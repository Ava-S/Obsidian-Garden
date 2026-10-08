As events are entities, we also might need [[Entity Resolution]] for events.

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

