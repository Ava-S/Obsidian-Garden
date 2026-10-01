[[OCED Core Model]]
## Definition
Events describe the occurrence of an observable phenomenon.

## Atomicity
An event is atomic meaning it refers to an observation taking place at exactly one point in time rather than having a duration.

### Thoughts
We have also modelled non-atomic events, think about the high-level events in BPIC14 and Task Instances (Eva) that have a start and end timestamp.

- Activity instance vs activity (https://link.springer.com/article/10.1007/s41066-020-00226-2)

- Maybe there is an additional concept needed to indicate non-atomic events. 
	- Could be non-atomic events, or interval events, or span events
	- And then we also have atomic events or point events

## Event Types
- Every event has exactly one event type. 
- In most use cases, the event type is the process activity that was performed, though other types of observations can be described as well (e.g. sensor recordings)
- Each defined event type has at least one event that instantiates it

#### Relationships between event types --> Composite Events
Through modelling, events can also become composite. So, we have atomic events, but two (or more) atomic events can create a composite event.
For instance
- atomic event e1 with event type *Create application Start* 
- atomic event e2 with event type *Create application Complete*

Then these two atomic events can be composed into a composite event e3 with event type *Create Application*. Event e3 *contains* events e1 and e2, and event type *Create Application* contains event types *Create application Start* and *Create application Complete*.

#### Use case
For Croma, we needed to know the composite events, i.e. when a medical device ENTERed and EXITed a station. I now modelled it using a PAIR relationship between the two events, but this could also have been done using a Composite event.

## Time
- Describes the moment in time where the event has been observed at.
- #implementation It captures both a timestamp conforming to ISO 8601-1:2019 and its resolution (ref. to the precision in which the timestamp was recorded).
	- Ava: I did not really think in this way about the resolution.  
	  We could consider that that the resolution must be consistent for all events. However, as data is often coming from different sources, this cannot be guaranteed (for instance, in BPIC14, the timestamps mentioned for the objects (incident, change and interaction) are date, hour, minute while the timestamps mentioned for the events are date, hour, minute, second
- #implementation At a minimum, the following precisions are to be differentiated: date, hour, minute, second, millisecond.
	- Ava: this is not a requirement I have, also data very often does not come in this shape. The lowest resolution I've witnessed is date (road traffic fine) and very often date, hour, minute.
	  I also don't want to add extra significancy than we have
- #implementation If the timezone is omitted, all timestamps are treated as UTC
	- Yes

## Event attribute values
- Each event has an arbitrary number of event attribute values and corresponding event attribute names, further describing the observation captured by the event as *attribute-value pairs*
- #implementation each event attribute value is captured as a string, boolean, integer, real, date, time or timestamp
- #implementation Each event attribute is related to exactly one event
- #implementation Each event attribute value is value of exactly one event attribute name
- #implementation Some information is typically represented with value-unit pairs (e.g. price and currency) describing parts of the same logically connected information
	- In such cases, it is #goodpractice to indicate relation by choosing the unit's event attribute name as the value's event attribute name suffixed with `_unit` (e.g. price and price_unit)

Ava: Yes, we also have attribute-value pairs and it is indeed good to logically pair value-unit pairs by convention.

#### Should all observations of an event be stored with the event?

The [[Events in OCED Core Model#Event attribute values]] suggests that observations captured by the event can be stored as attribute-value pairs belonging to that event. 

For instance, the MM gives the following example of event attribute value
	`transaction currency = USD`
	`merchant name = Emirates Airlines`
These examples, don't describe the event itself, but rather observed objects, so the event observed a `Transaction` of which the `currency = USD`, or the event observed a `Merchant` of which the `name = Emirates Airlines`. 

I take a different view, I would say that event attribute values should describe the event itself, not the state of an object it observed. 
As a result, there are not many event attributes that I have stored.

## Uniqueness + event identifiers
- Each event needs a *unique event identifier* that objects can refer to
- #question does this identifier need to be exposed?