
- This falls outside the scope of conceptualization, and is for performance gains
- This is still to be explored whether we need indexes on events, for performance gains
	- It could be interesting to create a range index on the timestamp of events to increase query speed
	- It could also be interesting to check whether an index on the event identifier is useful --> if not, then maybe we don't need an identifier, but I think it would still enforce reasoning on whether events are unique or not.