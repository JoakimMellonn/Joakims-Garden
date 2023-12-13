
Joakim Rosenfeldt Pedersen: 202207262
Thomas Ploughgaard: 202205767


## 1. NGOs

**a. SQL DDL: change the supporter schema to include a level column.**

We have used the DDL command `ALTER`, to alter the table and add the attribute `level`, and set the type to `INT`, and a default value of 0.
```SQL
ALTER TABLE Supporter ADD COLUMN `level` INT DEFAULT 0;
```


**b. SQL DML: Update the level for the supporter with the email address lucy@yahoo.dk to reflect the number of times she has donated to KDG.**

To update the supporter's level with the amount of times they have donated to the NGO 'KDG' ('MDGA'), we use a subquery to find the amount of times they have donated and use count method to get the number.
```SQL
UPDATE Supporter AS s
SET `level` = (SELECT count(*) FROM Donations WHERE s_id = s.id AND ngo_name = 'MDGA')
WHERE email = 'lucy@yahoo.dk';
```


**c. Give a trivial functional dependency for one of the tables**

In the NGO table, the primary key is `name`, so any attribute/set of attributes that includes `name` will have a trivial functional dependency. For example: `{name, based_in} → name` is a trivial functional dependency.


**d. List all non-trivial functional dependencies for the tables. Provide an explanation for your choices.**

Non-trivial dependencies are if A → B and B is not a subset of A.
This means that the non-trivial dependencies for the tables are:

NGO:
	`name` → `based_in`, `cause`, `director`, `phone`, `revenue`
	`phone` → `name`, `based_in`, `cause`, `director`, `revenue`

Supporter:
	`id` → `name`, `email`, `phone`, `city`, `NGO_name`, `birthday`, `vulenteer`
	{`email`, `NGO_name`} → `id`, `name`, `phone`, `city`, `birthday`, `vulenteer`

Donations:
	{`s_id`, `ngo_name`, `date`, `amount`} → `activity`


**e. Explain which functional dependency is causing redundancy and give an example of a type of anomaly that could occur from this redundancy.**

The supporter can only be connected to a single NGO since `ngo_name` is unique. This is a functional dependency which causes redundancy, if a supporter wishes to contribute to multiple NGOs, there will have to be multiple supporters with the same info, but different `ngo_name`'s.
This causes an Update anomaly, when trying to update a supporter's info, you'll have to update the same info in multiple rows.


**f. What are the candidate keys for these tables?**

A candidate key is an attribute or combination of attributes, that can qualify as a unique key.

NGO: 
	`name`,
	`phone`
Supporter: 
	`id`,
	(`email`, `ngo_name`)
Donations:
	(`s_id`, `ngo_name`, `date`, `amount`)


**g. Provide an example for a superkey that is not a candidate key for one of the tables.**

From the NGO table a superkey could be (`name`, `based_in`, `cause`). Since the superkey can uniquely identify a row in the table, but doesn't only have columns that are uniquely identifiable.


**h. Drop the attribute id in the supporter table. What would be the consequences of different triggered actions?**

Because of the Donations table having the `NOT NULL` and `ON DELETE CASCADE` on the foreign key that is the Supporter's id attribute, it will delete all rows in the Donations table.


**i. Describe a sequence of changes to the database schema that allows dropping the attribute id while still retaining all other relevant information?**

To drop the attribute `id` for the supporter table, you would need to create a new primary key. In this case we would use the `email` and `ngo_name` attributes to create a composite key. Since the combination of `email` and `ngo_name`, are unique for each supporter.
Then you would also need to remove the attribute `s_id` from the donations table. We would then add the email from the supporter instead, in this case as `s_email`. The primary key for donations would then also have to have the `s_email` instead of `s_id`.


## 2. University

**a. Show that you can derive the dependency {R, DH, S, Y} → {I, D} from others. Step by step, list each of the rules you apply.**

Steps:
1. Decomposition: We can use decomposition to say that {R, DH, S, Y} → {C}.
2. Transitive: Since we have that {C} → {D, CT}, {D, CT} → {I} and {I} → {D}, we know that we have both {R, DH, S, Y} → {I} and {R, DH, S, Y} → {D}.
3. Additivity: Now we can use additivity to put them together and get: {R, DH, S, Y} → {I, D}.


**b. Compute the closure of {R, DH, S, Y}, providing the steps taken.**

We have to compute {R, DH, S, Y}$^{+}$.

1. We can start with {R, DH, S, Y} → {C, SN}.

Now we have {R, DH, S, Y, C, SN}.

2. Now we know {C} an from here we know {C} → {D, CT}

{R, DH, S, Y, C, SN, D, CT}

3. From {D, CT} we can use {CT} → {CH} and {D, CT} → {I}.

{R, DH, S, Y, C, SN, D, CT, CH, I}

4. We can go back and use {C, SN, S, Y} → {R, DH, NS} to get {NS}

{R, DH, S, Y, C, SN, D, CT, CH, I, NS}


**c. Find the candidate keys of R based on F.**

From b we found that {R, DH, S, Y} is a candidate key of R.
Since {C, SN, S, Y} → {R, DH, NS}, we can get {R, DH, S, Y} from {C, SN, S, Y}, and therefore it is also a candidate key of R.