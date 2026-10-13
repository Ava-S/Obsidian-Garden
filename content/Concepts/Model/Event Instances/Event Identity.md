 
# Why do we need an identifier
  Having an identifier can be useful for the following things (see [[Keys]])
 - enforcing data integrity
- allowing the referencing of objects/database entities
	- In property graphs, relationships are represented with edges rather than foreign keys, and consequently, **keys are not needed for intra-database referencing**.
	- However, **a reference mechanism is still required by external applications** that access the database.
- allowing the identifying of objects

## Events don't have a name...

## ...but they do have an identity
- All properties of the event that make the event the event is what identifies the event
	- This could be timestamp + event type
	- This could be timestamp + event type + object it executed on
	- This could be timestamps that are sufficiently close in time + location + resource
	- This could be timestamp + some unknown properties that need to be inferred
	---> there is an **(unknown) event identity function** that uniquely identifies events
- At some point, someone has to decide which properties together form the event. 

## After applying the event identity function, we can *name* the event
- We can create an artificial *string* identifier to conveniently give it a name so we can enjoy the benefits of being able to reference and identify the event
