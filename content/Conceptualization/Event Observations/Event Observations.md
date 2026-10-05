*How do event observations appear in data?*

# Event Log
## Definition
- Every record describes an event with additional attributes. These additional attributes don't all necessarily belong to the event.
## Input
- **Timestamp**: List of attribute names that together form a timestamp (very often this is a single attribute, but I've seen cases where date and timestamp are split)
- **Event Type**: List of attribute names that together form the event type (very often this is activity (but it can also be another attribute), and can be accompanied by additional attributes like lifecycle).

- *Nice to have* (but unfortunately not always present)
- A key (identifier) for the event that uniquely identifies the event. 
![[Event Log (Data).png]]

# Object Data
- In object data, every record describes an object with additional attributes. These additional attributes often do belong to the object.
- Objects can be created, updated or deleted. Sometimes, these timestamps are kept track of as attributes (e.g. BPIC14 Open Time and Close Time for Interactions).
- These timestamped attributes represent an event that was executed on the specific object--> 
  so can be modeled as events

## Input
- **Timestamp**: List of attribute names that together form a timestamp and represent a phenomenon that occurred on the object.
- **Event Type**:
	- Either manual input for the event type.
	- The attribute names together could also form the event type --> At the moment PromG only supports setting a value using the attribute value or manual (so the attribute names together is not supported)

- **Event Identifier**
	- These events don't have an event identifier. One could easily be constructed by, for instance, concatenating the object id with the event type (or similar).
	- However, careful attention needs to be paid to duplicate events and batch events
	  i.e. if an object is not unique, then a single object might have multiple attributes associated for open and close
	- #example In BPIC14, a change can be opened exactly once, but closed multiple times. This results in a single change having multiple records.
		- Because a single change can appear multiple times, then for each open time and close time an event could be created. However, the two open events are actually the same one, while the two close events are different ones. This is something that needs to be addressed.

![[Object Data.png]]
# Sensor data
- This data can be come in many different forms and flavors. I will now highlight the two that I have seen, but this list is not exhaustive.
## Croma: each sensor had its own csv file.
- **Timestamp**: List of attribute names that together form a timestamp of when the scanner was activated.
- **Event Type**: the name of the file. I found it easiest to just set the value manually.
- Event identifier: not present
  Each scan represents a unique event (so every record id could act like a unique event id on the level of sensors)
	These scans were in itself not so interesting, but rather in what they represented. An scan indicating an object enters the washing machine is interesting, because this indicated the start of washing. From this perspective, a lot of noise (accidently scanning twice) was generated because items could be scanned multiple times after each indicating they went into the washing machine, while in reality the object probably only was washed once.  
	Multiple objects could be washed together, so we would also see multiple objects being scanned in quick succession indicating a batched event.

	To make sense of these scans, the scans needed to be cleaned a lot to ensure that the scans aligned with what we would expect (e.g. only entering washing machine once).

![[Croma Sensor Data.png]]

## Croma Simulation Data
- **Timestamp**: List of attribute names that together form a timestamp of when the scanner was activated. it represents the number of milliseconds passed since the simulation started.
- **Event Type**: the name of the file. I found it easiest to just set the value manually.
- **Event Identifier**: Not present
- How to deal with uniqueness: Each scan represents a unique event 

## NXP: Fault Detection and Classification Data (FDC Data) from a dicer machine (this machine cuts wafers into smaller dies).

- For each seconds, measurements of different sensors were included. Some of these sensors represented events such as Cutting Start and Cutting End.
- For these event sensors, it was determined how many seconds ago this sensor was activated. i.e. how long ago the event took place.
- **Timestamp**: List of attribute names that together form a timestamp of when the sensor was activated.
- **Event Type**: manual input for the event type.
- **Event Identifier**: not present
- Uniqueness of events: batching was possible, so not every observed event was unique.
	- As soon as there is a gap in recording, we cannot ensure that all events have been recorded, but we at least know that we might miss events.
- All events recorded --> unsure
![[NXP Sensor Data.png|700]]