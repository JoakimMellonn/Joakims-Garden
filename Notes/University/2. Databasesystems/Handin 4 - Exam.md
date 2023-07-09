
## Database design
**Convert the E/R diagram to a relational schema.**

First I'll map the regular entity sets to the relational schema:

Item(<u>item_no</u>, details)
Customer(<u>customer_no</u>, name)

Now I can map the weak entity set:

Item(<u>item_no</u>, details)
Customer(<u>customer_no</u>, name)
Purchase(<u>purchase_no</u>)

Now the 1:N relationships:

Item(<u>item_no</u>, details)
Customer(<u>customer_no</u>, name)
Purchase(<u>purchase_no</u>, customer_no)

Lastly the M:N relationships:

Item(<u>item_no</u>, details)
Customer(<u>customer_no</u>, name)
Purchase(<u>purchase_no</u>, customer_no)
Contains(<u>item_no</u>, <u>purchase_no</u>, quantity)



## Normalization
**1. Miniworld to functional dependencies.**
**Determine all full non-trivial functional dependencies of this relation, and provide your reasoning.**

1.  `Product_ID -> Product_Name`: Each product ID uniquely determines the product name.
2. `Product_ID -> Item_Price`: Each product ID uniquely determines the item price.
3.  `Customer_ID -> Customer_Name`: Each customer ID uniquely determines the customer name.
4.  `Date, Customer_ID, Product_ID -> Total`: The total is determined by the date, the customer ID and the product ID.

These functional dependencies are all three non-trivial, because none of them can be derived from any other dependency in this set.


**2. Decomposition**
Consider the relation R={X, Y, Z, S, T, U, V, W, Q, N} and the set of functional dependencies:

F={
	{X, Y} → {Z},
	{Y} → {W},
	{X} → {S, T},
	{X, Y} → {Q},
	{Y} → {U},
	{Z} → {Y},
	{X, Y} → {V, W, S},
	{U} → {V, W},
	{S} → {Q, N},
	{X, Z} → {S}
}

**Which normal form is this relation in? Decompose to the highest possible normal form. For each decomposition, describe the steps you go through and if the ensuing relations are in a higher normal form. Also state whether each decomposition is lossless, and whether it is dependency preserving.**

The relation $R$ is in 1NF because all the attributes have atomic values. To decompose this relation to the highest possible normal form, I need to find the candidate keys for $R$. From the given functional dependencies, I can derive that {X, Y} are a candidate key for $R$.

Since there are non-prime attributes that are dependent on a subset of the candidate key (partial dependencies), this relation is not in 2NF. To bring it to 2NF I need to remove these partial dependencies by decomposing $R$ into three relations: $R1$={X,Y,Z,V,W}, $R2$={X,S,T,Q,N} and $R3$={Y,U}. This decomposition is both lossless and dependency preserving.

$R1$ and $R3$ is already in 3NF because there are no transitive dependencies. However $R2$ is not in 3NF because there are transitive dependencies. To bring it to 3NF I need to remove these transitive dependencies by decomposing $R2$ into two relations: $R2_1$={X,S,T} and $R2_2$={S,Q,N}. This decomposition is both lossless and dependency preserving.

All resulting relations ($R1$, $R2_1$, $R2_2$ and $R3$) are now in 3NF, because there are no more transitive dependencies or partial dependencies. They're also in BCNF, because for all the relations the determinant of the non-trivial functional dependencies is a superkey.



## Multi valued dependency
**Consider the potential multivalued dependencies star_name —>—> street, city and movie_title—>—> star_name. Determine whether each MVD holds, may hold or does not hold and explain why.**

The MVD star_name —>—> street, city may hold because I assume an actor can have the same street address in two different cities.

The MVD movie_title —>—> star_name does not hold because a movie can have multiple actors. This means that if two tuples share the same movie_title value but still have different star_name values, it is not guaranteed that there exists two other tuples with the same star_name values but different movie_title values.



## SQL

- **NGO** (name, based_in, cause, director, phone, revenue) 
- **Supporter** (name, email, phone, address, zip_code, city, birthday) 
- **Supports** (ngo_name, email, volunteer, level) 
- **Donations** (activity, amount, date, email, ngo_name)

**1. Origins**
**Based on the above relational schema, what can you deduce about the ER-diagram that it was created from: which entity sets, relationship sets, and cardinality ratios can you deduce from this schema?**

I have three entity sets NGO, Supporter and Donations and one relationship set Supports.
Neither the NGO and Supporter have any foreign keys, and therefore they are strong entities. While the Donations entity set is dependent on both NGO and supporter, and is therefore a weak entity.

There is a relationship between NGO and Supports, since Supports have a foreign key (ngo_name) and the NGO doesn't, I know the have a 1:N relationship. NGO does also have a 1:N relationship with Donations.
The relationship between Supporter and Supports is also a 1:N relationship, with Supporter also not having any foreign keys and Supports having the email key. The last relationship between Supporter and Donations is also a 1:N relationship.
From this I know that the cardinality ratio between NGO and Supporter is M:N, because I have the Supports relationship set which have a 1:N relationship with both NGO and Supporter.



**2. Create statement**
**Write SQL DDL statements to define the two new relations, Supporter and Supports.**

For the `Supporter`, I assume their name can't be more than 50 characters, and same with the email. With the email I check that it has the correct pattern of an email using the `LIKE` statement. The phone and zip code, can only be numbers and have specific lengths, therefore I set them as specific length chars and checked using RegExp that it only contains numbers. 
For the address, I don't assume it can be longer than 50 characters (the longest street name in Denmark is 27). I check the address using a RegExp pattern, which checks that it starts with a letter, ends with a whitespace followed by a number, and has an arbitrary number of character in between. This did find an address which started with a whitespace, and I got an error from that until I changed the address.
For the birthday, I check that they're older than or 18 years old, by comparing their birthday to the `SYSDATE()`. 

For the relation `Supports`, I use the foreign keys `ngo_name` and `email`. With the bool `volunteer` I assume that if not specified, they're not volunteering, so the `DEFAULT` is false. And the level has the `DEFAULT` set to 0, as specified in the specifications.

```MySQL
CREATE TABLE `Supporter`(
    `name` 		VARCHAR(30)		NOT NULL,
    `email` 	VARCHAR(50) 	UNIQUE NOT NULL 	PRIMARY KEY,
    `phone` 	CHAR(8)			UNIQUE NOT NULL,
    `address`	VARCHAR(50)		NOT NULL,
    `zip_code`	CHAR(4),
    `city`		VARCHAR(50),
    `birthday`	DATE			NOT NULL,
    CHECK(phone REGEXP '[0-9]{8}'),
    CHECK(email LIKE '%_@_%._%'),
    CHECK(address REGEXP '^[[:alpha:]].*([[:space:]][0-9]+)$'),
    CHECK(zip_code REGEXP '[0-9]{4}'),
    CHECK(DATE_FORMAT(SYSDATE(), '%Y') - DATE_FORMAT(birthday, '%Y')
    - (DATE_FORMAT(SYSDATE(), '00-%m-%d') < DATE_FORMAT(birthday, '00-%m-%d')) >= 18)
);

CREATE TABLE `Supports`(
	`ngo_name`	VARCHAR(30) 	NOT NULL,
    `email`		VARCHAR(50)		NOT NULL,
    `volunteer` BOOLEAN			DEFAULT FALSE,
    `level`		INT				DEFAULT 0,
    FOREIGN KEY (ngo_name) REFERENCES NGO(name)
	ON UPDATE CASCADE ON DELETE CASCADE,
    FOREIGN KEY (email) REFERENCES Supporter(email)
	ON UPDATE CASCADE ON DELETE CASCADE,
    PRIMARY KEY (ngo_name, email)
);
```



**3. Update**
**Update _level_, as the number of donations the supporter made to an NGO, for all entries in Supports using a single update statement.**

To update the level of all Supporters to be the number of donations the supporter has made to an NGO. I'm going to count the amount of times the each supporter have donated to a specific NGO, and then set the level to that count.

```MySQL
UPDATE Supports AS s
SET level = (
	SELECT count(email)
	FROM Donations AS d
	WHERE d.email = s.email AND d.ngo_name = s.ngo_name
);
```



**4. Triggers**
**Ensure that the 'level' of an NGO supporter is updated correspondingly whenever they make a donation to the NGO.**

To update attributes whenever something happens, I need to create a trigger on the action I want to track. In this case, I need to create a trigger on insert on the `Donations` table. Since I assume that donations cannot be undone, and therefore levels will only go up, I'm incrementing the level of the Supporter by one. I'm using the `new.email` to get the `email` of the affected Supporter.

```MySQL
CREATE TRIGGER `after_donation_insert`
	AFTER INSERT ON Donations
    FOR EACH ROW
UPDATE Supports AS s
SET level = level + 1
WHERE s.email = NEW.email AND s.ngo_name = NEW.ngo_name;
```



**5. Indexes**
**Create an index on Supports on the attribute ngo_name, so it is faster for an NGO to retrieve its supporters.**

To create an index on Supports I use `CREATE INDEX` and give the index a name, in this case I've named it "supports_ngo". Then I need to specify what attribute the index is on, and that is the `ngo_name` in this case.

```MySQL
CREATE INDEX `supports_ngo` ON Supports(ngo_name);
```


**What type of index is this? Primary, secondary, dense, sparse, clustering or not?**

It's a clustering index, because when indexing a table on a non-key row, they will be clustered. In this case I index it on the ngo_name attribute, while the key of the Supports table is the ngo_name and email combined.


**Let us now assume that this index is a 2-level (height 2) clustered B-tree index; to find all the supporters of KDG using this index, how many I/O operations are needed? Describe which additional assumptions you must make to be able to derive your answer.**

It would require at most three I/O operations, the first operation is to read the root node of the tree, the second is to read the leaf node containing the first occurrence of KDG. Since it's a clustered index, all entries (supporters of KDG), will be stored adjacently on the disk, and this means the third operation would be to read the block containing all supporters of KDG.
To do this I assume that all supporters of KDG can fit into one block on the disk.



**6. View and grant permission**
**Suppose KDG has access to the information on their supporters and they would like to be able to share an overview of this data with others. Concretely, they want to show simple statistics of how many supporters they have at each level of support.**

**Create a view that extracts this overview statistics, and grant the already existing user account StatNerd permission to query the view and to let others query the view as well.**

To grant the StatNerd user access to get the simple statistics about how many supporters KDG has at each level, I first need to create the view to grant access to. To do this I use `CREATE VIEW` give it the name `kdg_statistics` and then create the query to the desired view.
In this case I need to count how many Supporters KDG has at each level. To get these statistics, I use the relation Supports, since it contains both the `ngo_name` and `level` attributes. I select the level and then count the amount of supporters by using `COUNT(*)`, then I specify that I only want those who support KDG, and finally I group by level.
To grant StatNerd access to the view I use `GRANT SELECT ON`, to only give "read" access for the statistics.

```MySQL
CREATE VIEW `kdg_statistics` AS
SELECT level, COUNT(*) as num_supporters
FROM Supports
WHERE ngo_name = 'KDG'
GROUP BY level;

GRANT SELECT ON kdg_statistics TO StatNerd;
```

**Can we also allow StatNerd the possibility to update this statistics? Provide a reasoning for your answer.**

I can't give StatNerd the ability to update the statistics from the view, since a view is a virtual table based on the result of a query. However, I can give StatNerd the ability to update the whole table `Supports`, with the following statement:

```MySQL
GRANT UPDATE ON Supports TO StatNerd;
```

This does give StatNerd full permission to update all data in the `Supports` table, so wether or not this is a good idea, depends on the situation.



**7. Schema modification**
**Issue an SQL DDL statement that will modify the relation schema Supporter such that it can also store the citizenship of supporters, which is assumed to be Danish unless specified otherwise, but which we may not necessarily know for all supporters.**

```MySQL
ALTER TABLE Supporter ADD COLUMN `citizenship` VARCHAR(30) DEFAULT 'Danish';
```



## Embedded databases
**Using either Python or Java, as in week 6's exercises, connect to the NGO database in NGO_final.sql.**

I have used python to connect to the NGO database, and then I've made query that gets the names of the NGOs in the database. 

```python
# exam_db_before_query.py

import mysql.connector
from mysql.connector import Error
try:
    connection = mysql.connector.connect(host='localhost',
                                         database='NGOs',
                                         user='root',
                                         password='**********')
    if connection.is_connected():
        cursor = connection.cursor()
        cursor.execute("select database();")
        record = cursor.fetchone()
        print("You're connected to database: ", record[0])
        
        QUERY = ("SELECT name FROM NGO")
        cursor.execute(QUERY)
        
        print('NGOs in database:')
        for result in cursor:
            print(result[0])
        
except Error as e:
    print("Error while connecting to MySQL", e)
finally:
    if connection.is_connected():
        cursor.close()
        connection.commit()
        connection.close()
```

**Change the program such that it finds the email of all the supporters who only support one NGO.**

To do this, I have changed the query to only select those whose email show up once in the Supports table. I've done this by grouping by email for those having the count of email being only 1.

```python
# exam_db_after_query.py

import mysql.connector
from mysql.connector import Error
try:
    connection = mysql.connector.connect(host='localhost',
                                         database='NGOs',
                                         user='root',
                                         password='**********')
    if connection.is_connected():
        cursor = connection.cursor()
        cursor.execute("select database();")
        record = cursor.fetchone()
        print("You're connected to database: ", record[0])
        
        QUERY = ("SELECT email FROM Supports GROUP BY email HAVING count(email) = 1")
        cursor.execute(QUERY)
        
        print('NGOs in database:')
        for result in cursor:
            print(result[0])
            
except Error as e:
    print("Error while connecting to MySQL", e)
finally:
    if connection.is_connected():
        cursor.close()
        connection.commit()
        connection.close()
```
