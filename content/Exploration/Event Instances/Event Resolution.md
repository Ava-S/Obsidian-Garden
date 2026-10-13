As events are entities, we also might need [[Entity Resolution]] for events.


# What makes an event unique and what is its identity?
Make them unique by time and relevant concept information
	- Events don't have a name --> identifier would be artificial for convenience to give it a name
	- All properties of the event that make it itself, what properties identify the event
		- It could be that not all properties of the event are in the data --> it could lead to incorrect events
		- Sometimes, we can inject **domain knowledge** to infer the missing properties (or something alike)
	- At some point, someone says these are the properties that together form the event.





## Examples of event resolution
#example
*What to do when assumption of explicit event identifier or unique event records (implicit event identifier) is violated?*

- NXP (resolved outside and inside EKG)
	- Discretize sensor recordings into events (outside EKG)
	- Merge different events into a single batch event (Therefore, we merge the events that happened simultaneously and at the same equipment ID into one event. This event is then correlated to all the wafers involved in that event.)

- GR3N (resolved outside and inside EKG)
	- Discretize sensor signals into low-level events (outside EKG)
	- Turn low-level sensor events into process-level movement events (within EKG)

- Croma (resolved within EKG)
	- Sensor events naturally had a one-to-one mapping to process-level events. So no event abstraction required.
	- However, as sensors could be triggered multiple times, there were multiple observations of the same event (removed in EKG)

- BPIC14 (resolved within EKG)
	- An OPEN change event could be imported twice, is merged in EKG.

