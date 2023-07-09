
Joakim Rosenfeldt Pedersen: 202207262
Thomas Ploughgaard: 202205767


## 1. Write DDL SQL statements

**a. Write the DDL SQL statement to create the database NGOs.**

```SQL
CREATE DATABASE IF NOT EXISTS `NGOs`;
```

**b. Write the DDL SQL statement to create the relation Supporter.**

```SQL
CREATE TABLE `Supporter`(
	`id` INT NOT NULL UNIQUE PRIMARY KEY,
    `name` VARCHAR(100) NOT NULL,
    `email` VARCHAR(100) NOT NULL UNIQUE CHECK (`email` LIKE '_%@_%._%'),
    `phone`	INT UNIQUE CHECK (`phone` > 9999999),
    `city` VARCHAR(100) NOT NULL,
    `NGO_name` VARCHAR(30) NOT NULL,	
    `birthday` DATE	NOT NULL CHECK (`birthday` LIKE '____-__-__'),
    `is_volunteer` BOOLEAN DEFAULT true,
    FOREIGN KEY (`NGO_name`) REFERENCES NGO(`name`)
    ON UPDATE CASCADE ON DELETE CASCADE
);
```


## 2. Write SQL statements to

**a. Insert a new supporter with ID 12345 to MDGA who would like to be a volunteer.**

```SQL
INSERT INTO Supporter
VALUES (
	12345,
	'Bo Obsen',
	'bo@obsen.dk',
	'87654321',
	'Middelfart',
	'MDGA',
	'1969-04-20',
	TRUE
);
```

**b. Update the name from MDGA to 'KDG' and the cause to 'Keep Databases Great'.**

```SQL
UPDATE NGO
SET name = 'KDG', cause = 'Keep Databases Great'
WHERE name = 'MDGA';
```

**c. Delete ONLY the Supporter that you inserted in a.**

```SQL
DELETE FROM Supporter WHERE id = 12345;
```


## 3. Write SQL queries to

**a. Find the name and phone number of all supporters who have a phone number specified and live in Aarhus.**

```SQL
SELECT name, phone
FROM Supporter
WHERE phone IS NOT NULL AND city LIKE '%Aarhus%';
```

**b. For each supporter of KDG, who has donated more than 1000 in total to it, find the total amount they have donated to the cause.**

```SQL
SELECT SUM(amount)
FROM Donations AS d
WHERE 1000 < (
	SELECT SUM(amount)
    FROM Donations
    WHERE s_id = d.s_id AND ngo_name = 'KDG'
    GROUP BY s_id
)
GROUP BY d.s_id;
```

**c. Find all supporters of any NGO who have made at least one donation of more than the average individual donation amount given to KDG.**

```SQL
SELECT *
FROM Supporter AS s
WHERE (
	SELECT DISTINCT s_id
	FROM Donations
	WHERE s_id = s.id AND amount > (
		SELECT AVG(amount)
        FROM Donations
        WHERE ngo_name = 'KDG'
	)
);
```

**d. For every NGO find all supporters who have made at least one donation of more than the average individual amount for that specific NGO.**

```SQL
SELECT *
FROM Supporter AS s
WHERE (
	SELECT DISTINCT s_id
	FROM Donations AS d
	WHERE s_id = s.id AND amount > (
		SELECT AVG(amount)
		FROM Donations
		WHERE ngo_name = d.ngo_name
	)
);
```
