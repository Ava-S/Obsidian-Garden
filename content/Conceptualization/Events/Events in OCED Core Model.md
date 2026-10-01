[[OCED Core Model]]
## Definition
Events describe the occurrence of an observable phenomenon.

## Atomicity
An event is atomic meaning it refers to an observation taking place at exactly one point in time rather than having a duration.

## Event Types
- Every event has exactly one event type. 
- In most use cases, the event type is the process activity that was performed, though other types of observations can be described as well (e.g. sensor recordings)
- Each defined event type has at least one event that instantiates it

## Time
- Describes the moment in time where the event has been observed at.
- #implementation It captures both a timestamp conforming to ISO 8601-1:2019 and its resolution (ref. to the precision in which the timestamp was recorded).
- #implementation At a minimum, the following precisions are to be differentiated: date, hour, minute, second, millisecond.
- #implementation If the timezone is omitted, all timestamps are treated as UTC

## Event attribute values
- Each event has an arbitrary number of event attribute values and corresponding event attribute names, further describing the observation captured by the event as *attribute-value pairs*
- #implementation each event attribute value is captured as a string, boolean, integer, real, date, time or timestamp
- #implementation Each event attribute is related to exactly one event
- #implementation Each event attribute value is value of exactly one event attribute name
- #implementation Some information is typically represented with value-unit pairs (e.g. price and currency) describing parts of the same logically connected information
	- In such cases, it is #goodpractice to indicate relation by choosing the unit's event attribute name as the value's event attribute name suffixed with `_unit` (e.g. price and price_unit)

## Uniqueness + event identifiers
- Each event needs a *unique event identifier* that objects can refer to
- #question does this identifier need to be exposed?