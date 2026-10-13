---
journal: Work Daily
journal-date: 2026-10-13
journal-notelet: Meeting w Dirk and Francesca
journal-notelet-index: 1
---
## Meeting with Dirk and Hosna

### Process entities
- Can we also have relators? 
- Relators vs objects
	- Endurants: are wholly presents at a given moment in time, which can qualitatively change while maintaining their identity.
	- Object --> existentially independent
	- Relator --> existentially dependent
- Reification might be for relators, but also for implicit objects that are not present in the data (for instance, the object connecting a order and a delivery is the item. An item is not existentially dependent on order and delivery, but might need to be reified if not present in the data)

### Dimensions for events
- Atomic <-> Complex
	- Atomic events have no proper parts
	- Complex events have proper parts
- Instantaneous <-> Durative
	- Instantaneous events have no duration
	- Durative events have a duration
- All combinations can occur

|         | Instantaneous                                             | Durative                                                 |
| ------- | --------------------------------------------------------- | -------------------------------------------------------- |
| Complex | - Place Order<br>(send order confirmation, book in items) | - Order Picking<br>(Pick item, pick item, pick item)<br> |
| Atomic  | - Send email                                              | - Drinking tea<br>- Waiting in line                      |

### Framework of thinking

![[Pasted image 20261013180853.png|324]]
It is good to keep this framework of thinking in mind.
For instance, we might know an event must have happened in reality, which is not present in the data, but we want to have it in model. 

### Events identity
There was also a discussion about [[Event Identity]] 

## Meeting with Hosna

### Open world vs closed world assumption

We cannot fully align with one assumption
- We do argue that data might be incomplete or incorrect --> so this is an open world, we do not know everything
- For analysis, we need closed world assumption
	- For instance, with DF a requirement is that two events are directly followed if there is no other event in between. In an open world, we would never know this was the case.

Very pragmatically, we could take the following stance
![[Pasted image 20261013184809.png|494]]

Reality is what is, we don't have to assume it is open world or closed world because these assumption tell something about the data and the models we have.

For the data, we can assume it is open world --> there are things we don't know, and inaccuracies
For the model, we assume it is closed world --> once we have modelled our data, we do assume everything is known. 

### Process of model building
![[Pasted image 20261013184959.png|538]]

Normalization vs resolution
- The same objects and events can appear multiple times in the source data because of different reasons
	- Data is not properly normalized and the same facts live in multiple places
		- This is very often the case for objects that are recorded via events
		- Object attributes are recorded for all events --> leading to repeated facts
		- We can fix this through normalization, **technical and well known**
	- There are multiple recordings of the same instance
		- Across different data sources
			- For instance, Den Haag and The Hague both refer to the same object 
			  --> object resolution (also well known)
			- Different sensors recording the same event
			  --> event resolution (not well researched)
		- Within a single data source
			- ?? Does this hold for objects??
			- Events are duplicated because they might act on multiple objects
			  OR different scans at slightly different times refer to the same events
			  --> Event resolution

Explicit vs implicit relationships
- Relationships might be explicit in the dataset or implicit via other relationships 
  This is both for O2O and E2O.

Domain level vs instance level
- Domain experts might identify entities and relationships and then proof for these can be found in the data on an instance level. This will require iterations. 
- 