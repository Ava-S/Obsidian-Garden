[[XES]]
## Definition
- Events represent atomic granules of activities that have been observed during the execution of a process.
## Atomicity
- Events are atomic (i.e. has no duration)

## Attributes
Event objects contain no information themselves, all information is an event log is stored in *attributes*, attributes their parent element (we also have log and trace next to event)

All attributes have a string-based key
	- no line feeds, no carriage returns, no tabs
	- keys must be *unique within their enclosing container*, except for those keys that are within an enclosing list, as the list already imposes an order on these keys
## Event Types ~ Event Classifiers --> #modeling
- Logs have an event classifier
- Event classifiers assigns to each event an identity, which makes it comparable to other events
- Classifiers are defined via a *set of attributes*, from which the class identity of an event is derived.
- Event classifiers are defined for the log, and there may be an arbitrary number of classifiers for each document.

## Concept:name (is an extension, i.e. not required)
- This represents the name of the, e.g. the name of the executed activity represented by the event 
## Time (is an extension, i.e. not required)
- time:timestamp --> the date and time at which the event occurred
- #implementation Date attributes hold information about a specific point in time (with milliseconds precision)
## Event attribute values
- Events may have additional attributes, defined using extensions
## Uniqueness + event identifiers
- There is concept:instance which identifies which instance of the concept:name (executed activity) it is. Again, this is an extension, so not required.
- There is identity:id that can be defined for events which is an unique identifier (UUID) for an element
