## Relation
Made up of:
- A **schema** specifies the name of the relation, plus the name and type of each column
- An **instance** is a table, with rows and columns
	- The number of rows = `cardinality`
	- The number of fields = `degree` / `arity`

A *relational database* is a set of relations

Each entity in an ER becomes a relation.
Attributes in an ER become attributes of the relation

---

## Keys
Way to associate tupes in different relations
They are one form of **integrity constraint** (`IC`)

> Example:
> Only students can be enrolled in subjects

##### Primary Keys
A set of fields is a **superkey** if no 2 distinct tuples can have same values in all key fields
A set of fields is **key** for a relation if it is a superkey and no subset of the fields is a superkey
Out of all keys, one is chosen to be the **primary key** of the relation. Other keys are called **candidate keys**
Each relation has a primary key --> can be more than one column (**composite key**)

```SQL
CREATE TABLE Enrolled
	(sid CHAR(20),
	 cid CHAR(20),
	 grade CHAR(2),
	 PRIMARY KEY (sid, cid)) -- composite primary key

-- use UNIQUE for candidate keys
```

##### Foreign Keys
Pointers to another table
A set of fields in one relation that is used to refer to a tuple in another relation
Must correspond to the primary key of the other relation
If all foreign key constraints are enforced, referential integrity is achieved

```SQL
CREATE TABLE Enrolled
	(sid CHAR(20),
	 cid CHAR(20),
	 grade CHAR(2),
	 PRIMARY KEY (sid, cid)) -- composite primary key
	 FOREIGN KEY (sid) REFERENCES Students
```

---

## Integrity Constraints
A condition that must be true for any instance of the database
They are specified when scheme is defined
They are checked when relations are modified

An instance is **legal** if it satisfies all specified ICs. We should not allow illegal ones!!

---

## Translating ER - Many to Many
```
Employee(*ssn*, name, age)
Department(*did*, dname, budget)
Works_In(**ssn**, **did**, since) -- Associative entity
```

```SQL
CREATE TABLE Employee
(ssn CHAR(11),
 name VARCHAR(20),
 age INTEGER,
 PRIMARY KEY (ssn))

CREATE TABLE Department
(did INTEGER,
 dname VARCHAR(20),
 budget FLOAT,
 PRIMARY KEY (did))

CREATE TABLE Works_In
(ssn CHAR(11),
 did INTEGER,
 since DATE,
 PRIMARY KEY (ssn, did),
 FOREIGN KEY (ssn) REFERENCES Employee,
 FOREIGN KEy (did) REFERENCES Department)
```

Specify total participation with ```
```
NOT NULL -- field cannot be empty
```
