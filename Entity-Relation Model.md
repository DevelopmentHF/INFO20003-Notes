
## Entity
Real world object distinguisable from other objects
Described in a database using **attributes**
An **entity set** is a collection of entities all of the same type

> Example entity:
> Employee > name (`attribute`), age, SSN (`key`)

The `key` is a unique identifier for an entity, has a solid underline

---

## Relationship
An association among two or more entities
Can have their own attributes
A relationship set is a collection of relationships of the same type

> Example relationship set:
> Employee **works in** Department

> Department > ID (`key`), name, budget
> Works in > since

The same entity set can participate in different relationship sets or different roles in the same set

---

## Constraints
**Key Constraints** determine the number of objects taking part in the relationship set

> Many to Many, One to Many, One to One
> I.e How are nodes connected to each other? Just connected to one node in the other set or multiple? etc etc

Many to Many is represented by a line in a diagram
>An `employee` can `work in` many `departments`
>A `department` can have many `employees`

One to many is represented by an arrow in a diagram
>Each `department` can have only 1 manager
>This is a key constraint on `manages` (relationship)


**Participation Constraints** explores if all entities of a set take part in a relationship
If yes --> *total* participation --> represented by a bold line
If no --> *partial* participation
>Every `employee` must `work in` a `department`
>Each `department` must have a manager, but not everyone is a manager

---

## Weak Entities
A **weak entity** can only be uniquely identified by considering another entity, the `owner`
Represented by a bold outline and a dashed underline for the `key`
Cannot exist on its own, only exists when coupled with an owner entity.
Must have total participation in this relationship set. 

---

## Ternary Relationships
Relationships can have `n` entity sets taking part, not just 2.

---

## Special Attributes

##### Multi-Valued
Attributes that can have multiple, but finite, values of the same type

> Employees have to have a home phone number and work phone number captured

Shown as a double ringed attribute in a diagram

##### Composite
Attributes which have a structure hidden inside
Each inner element can be of a different type

> Address > Postcode, St Name, St Num

---

## Conceptual Design

Choices to make:
- Should a concept be an entity, attribute or relationship?
- Should a relationship be binary, ternary or n-ary?

> Should address be an attribute of employee or an entity related to employees?
> Depends on how we want to use the information. IF we have several addresses per employee, address must be an entity

