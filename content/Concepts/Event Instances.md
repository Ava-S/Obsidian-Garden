## Definition 

> An event instance represents the occurrence of a phenomenon at a particular point in time. Each event instance represents a distinct occurrence. Event instances are also referred to as events. 
## Origin
Event instances may be observed in source data or inferred from available information. 
## Characteristics
- Every event is atomic, i.e. occurs at a single point in time. 
- Every event has exactly one event type
- Every event carries a timestamp
- Every event has a unique event identifier that identifies its distinct occurrence.
- An event may have additional attributes
## Distinction from related concepts

| Concept           | Difference                                                                                                                                                           |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Event Type        | The type describes a kind of event that may occur. An event instance instantiates an event type by representing a particular occurrence of that type.                |
| Activity instance | An activity instance represents a phenomenon that extends over a period of time.                                                                                     |
| Event observation | An event observation represents a (partial) recording of an event instance in a particular source. Multiple event observations may refer to the same event instance. |
## To-dos
- [ ] Work out event types
- [ ] Work out timestamp
- [ ] Work out attributes
## Open questions
- I'm not sure if we need to add *within a process* to the definition. OCEL1.0, 2.0 and XES explicitly mention process, while OCED does not mention it. 