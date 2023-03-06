## Data vs Information

### Data
- Known facts that are **stored** or **recorded**
	- Includes text, numbers, objects
### Information
- *Data* **presented** in context
	- Could be displayed in a pie chart for example
- Data that has been processed to increase the users knowledge, typically more meaningful

>Data is known and available, information is processed and useful

---

## #Metadata

Described as data about data.
> Acts like a data dictionary

Can include `structure` ,`rules`, `constraints` for the database
We need it for **consistency** and **meaning** to prevent 'rubbish' data being entered.

---

## What is a database?

A large, integrated, **structured** collection of data.
Typically intended to model some real world enterprise.

A Database Management System (DBMS) is a software system designed to store, manage and faciliate access to databases. We use mySQL.

---

## Databases vs File Processing Systems

FPS allows for a *duplication* of data (**bad!!**) as there are multiple programs all with the own files.

Allows for `inconsistency` in data as files need to be updated in multiple places.
Limited ability for data sharing, lengthy development times, excessive program maintenence, as well as program-data dependence.

Databases can manage this data in a structured way, typically in a relation model.
>Stores data in the form of tables like excel spreadsheets with rows and columns forming relations
>Keys allow us to link relations/tables

Allows for data independence, minimal redundancy (normalisation), consistency, improved sharing and maintenance.

