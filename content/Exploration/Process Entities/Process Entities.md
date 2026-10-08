# Definition
> An entity is something you want to store information about
>    [https://database.guide/what-is-a-database-entity/](https://database.guide/what-is-a-database-entity/)

> An entity is a distinct, independent object or concept in the real world that can be represented in a database (e.g. a person, place, thing, event or concept) 
> [https://www.clrn.org/what-are-entities-in-database/](https://www.clrn.org/what-are-entities-in-database/)

> Entities possess attributes, which are properties or characteristics that describe the entity  [https://www.clrn.org/what-are-entities-in-database/](https://www.clrn.org/what-are-entities-in-database/)

# Types of entities in Process Mining
We distinguish between different types of entities

- [[Conceptualization/Events/Event Instances/Event Instances]]: describes the occurrence of an observable phenomenon
- [[Event Types]]: the kind of observation described by events (could be stored together with event, but it proves useful to treat this as its own entity)
- [[Objects]]: either represents something tangible (e.g. persons, locations, machines, documents, document line items) or abstract (e.g. legal entities, organizational constructs, and electronic documents)
- [[Object Types]]: the kind of object (could be stored together with object, but it proves useful to treat this as its own entity)

# Taxonomy
Following the taxonomy provided by https://doi.org/10.1007/s41066-020-00226-2, we have

- **Events vs activities**
	- **Activities** are the work packages that are instantiated within instances of the process. The history of execution of these activities is stored within event logs for a posteriori analysis. 
		- The *business activities* (i.e., the concepts known at business level) can differ significantly from the corresponding events stored in the event log, since the underlying system might not operate on the same conceptual level.
	- **Events** represent the records within these event logs. Note that, the execution of one activity in a process instance can be reflected by multiple events, e.g., when event logs record both the start and completion of an activity.
- **Instances vs classes**
	- A **class** describes that an event/activity may potentially executed for some instance of a process
	- An **instance** describes the actual execution of some class


