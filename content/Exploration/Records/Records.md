# Definition

> A record is a single collection of related values stored as one unit [https://whatisdatabase.com/what-is-a-record-in-a-database-with-examples](https://whatisdatabase.com/what-is-a-record-in-a-database-with-examples)

- In tables or CSV files, every row is a record
- In JSON, a collection of key-value pairs is a record

# What does a record describe?

A record should ideally describe one thing.
- If a table/JSON stores application, then each record describes/represents an application.
- If a table/JSON stores events, then each record describes/represents an event.

I say ideally because each attribute should be describing the thing, but this is not always the case.

## Event Logs
- #example For instance, the data in BPIC17, each record represents an event. However, not all attributes describe the event directly.
- I've put all attributes of the BPIC17 below in order they appear in the CSV, what they describe and whether they are describing the event.
- I also took some of the answers from the BPIC17 documentation ([https://ais.win.tue.nl/bpi/2017/challenge.html](https://ais.win.tue.nl/bpi/2017/challenge.html))

|                       |                                                                                                    |                                                                                                  |
| --------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Attribute             | Description                                                                                        | Describing the event?                                                                            |
| Case                  | The application ID (the application observed through the event)                                    | Yes                                                                                              |
| Event                 | The activity that is executed                                                                      | Yes                                                                                              |
| Time                  | At what date and time did the event occur                                                          | Yes                                                                                              |
| lifecycle:transition  | The lifecycle information of the activity (Complete, schedule, withdraw)                           | Yes                                                                                              |
| ApplicationType       | The type of application (new credit/existing loan takeover)                                        | No, describes the application                                                                    |
| LoanGoal              | The reason the loan was applied for (e.g. Home improvement, existing loan takeover)                | No, describes the application                                                                    |
| RequestedAmount       | The requested loan amount in euros                                                                 | No, describes the application                                                                    |
| MonthlyCost           | The monthly cost for the offer                                                                     | No, describes the offer                                                                          |
| org:resource          | The resource that performed the event                                                              | Yes                                                                                              |
| Selected              | Whether the offer was selected                                                                     | No, describes the offer                                                                          |
| EventID               | Unique identifier of the event (Application ID/Offer ID when activity is create Application/Offer) | Yes                                                                                              |
| OfferID               | The offer ID (the offer observed through the event)                                                | Yes                                                                                              |
| FirstWithdrawalAmount | The initial withdrawal amount                                                                      | No, describes the offer                                                                          |
| Action                | I think this is the effect of the event on the observed application/offer                          | Yes?                                                                                             |
| Accepted              | Whether the offer was accepted by the customer                                                     | No, describes the offer                                                                          |
| CreditScore           | The credit score of the customer                                                                   | No, describes the customer (however, there is no customer Id, so could also belong to the offer) |
| NumberOfTerms         | The number of payback terms agreed to                                                              | No, describes the offer                                                                          |
| EventOrigin           | Whether the event originated from observing an application, offer or workflow                      | Yes                                                                                              |
| OfferedAmount         | The offered amount                                                                                 | No, describes the offer                                                                          |

**The data is very often not in First Normal Form (1NF), therefore the same type of information is often repeated.**

--> What I do is to split the records to its own separate entities (actually transforming it into 1NF). So, in an EKG, every node describes its own thing (entity).

*TODO: look into functional dependencies between attributes and primary keys*

## Temporal attributes in records

It is unknown when some values were recorded. The fact that they appear together with a specific timestamp, does not mean the value of these attributes were known at that time.

For instance, when the offer is created, the accepted and selected attributes are already set to True or False, even though these values are not known at that time.

Similarly, almost only accepted offers have a credit score > 0, so it seems that this credit score is only set when the offer is accepted (in BPIC17 dataset)

### Event-level and case-level attributes
- In a classical event log, attributes are either categorized as an event-level attribute or a case-level attribute
	- Either an attribute describes the event (and can change per case) 
	- An attribute describes the case (and remains static per case).

This is a too simplistic view. An object (case in classical process mining) can have evolving attributes that are "updated" via an event. For instance, an offer can go from not accepted to accepted.

This would be considered an event-level attribute, even though it actually belongs to an object.

## Dependencies between attributes

- Though in an event log, every record should just describe the event, this is very often not the case.
- An event log does not only point to other objects the event is related to, but also contains attributes (that may evolve over time) of those attributes
- Therefore, we need to disentangle the records into the different entities they are describing.