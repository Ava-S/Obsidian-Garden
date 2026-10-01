# Composite Events
Through modelling, events can also become composite. So, we have atomic events, but two (or more) atomic events can create a composite event.
For instance
- atomic event e1 with event type *Create application Start* 
- atomic event e2 with event type *Create application Complete*

Then these two atomic events can be composed into a composite event e3 with event type *Create Application*. Event e3 *contains* events e1 and e2, and event type *Create Application* contains event types *Create application Start* and *Create application Complete*.


# Time
- Ava: I did not really think in this way about the resolution.  
    We could consider that that the resolution must be consistent for all events. However, as data is often coming from different sources, this cannot be guaranteed (for instance, in BPIC14, the timestamps mentioned for the objects (incident, change and interaction) are date, hour, minute while the timestamps mentioned for the events are date, hour, minute, second
- At a minimum, the following precisions are to be differentiated: date, hour, minute, second, millisecond
	- Ava: this is not a requirement I have, also data very often does not come in this shape. The lowest resolution I've witnessed is date (road traffic fine) and very often date, hour, minute.
- If the time zone is omitted, all timestamps are treated as UTC.

- Ava: yes, I also make this assumption. I do not allow that for some timestamps a time zone is allowed and for others not. TODO Ava: check in implementation whether this is actually true.

## Event Attribute Value
Ava: Yes, we also have attribute-value pairs and it is indeed good to logically pair value-unit pairs by convention.

# Should all observations of an event be stored with the event?

The [[OCED Core Model#Event attribute values]] suggests that observations captured by the event can be stored as attribute-value pairs belonging to that event. 

For instance, the MM gives the following example of event attribute value
	`transaction currency = USD`
	`merchant name = Emirates Airlines`
These examples, don't describe the event itself, but rather observed objects, so the event observed a `Transaction` of which the `currency = USD`, or the event observed a `Merchant` of which the `name = Emirates Airlines`. 

I take a different view, I would say that event attribute values should describe the event itself, not the state of an object it observed. 


