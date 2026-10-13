

## Definition 

> An event instance represents the occurrence of a phenomenon at a particular point in time. Each event instance represents a distinct occurrence. Event instances are also referred to as events. 
## Origin
Event instances may be observed in source data or inferred from available information. 
# Reality - Data - Model
- Event instances are on the model level. 
## Characteristics
- Every event is atomic, i.e. they don't have parts
- Every event is [[Instantaneous|instantaneous]], i.e. they don't have a duration 
- Every event carries a timestamp
- Every event has exactly one event type
- Every event is [[Event Identity|uniquely identified by some properties]], which is serialized into an identifier for convenience.
- **An event may have additional attributes**
	- Proper event attributes have not been witnessed by either me or Hosna
	- If temporality of objects is not modelled, then event attributes could act like a place for updated values towards objects (however, how to deal with multiple changes at once)
- An event is in the past and they happened. 
- An event and its attributes are immutable (obvious for instantaneous events). 
- An event has a role in the process.

## Distinction from related concepts

| Concept           | Difference                                                                                                                                                           |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Event Type        | The type describes a kind of event that may occur. An event instance instantiates an event type by representing a particular occurrence of that type.                |
| Event observation | An event observation represents a (partial) recording of an event instance in a particular source. Multiple event observations may refer to the same event instance. |
## To-dos
- [ ] Work out event types
- [ ] Work out non-instantaneous/non-atomic events
- [ ] Work out activity (executions) and types 
- [ ] Work out timestamp
- [ ] Work out attributes
## Open questions
- ~~I'm not sure if we need to add *within a process* to the definition. OCEL1.0, 2.0 and XES explicitly mention process, while OCED does not mention it.~~ 
	- ~~Events must do something --> events must play a role~~
	- ~~Every element should play a part.~~
- 