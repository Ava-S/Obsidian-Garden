
|                                             | [[Events in OCED Core Model\|OCED Core Model]]                 | [[Events in OCEL1.0]]                                                              | [[Events in OCEL2.0\|OCEL2.0]]                                 | [[Events in XES\|XES]]                                                                        | [[Ava; follows mostly OCED]]                                                                                                                                 |
| ------------------------------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| *within a process*                          | Not specified                                                  | ✅                                                                                  | ✅                                                              | ✅                                                                                             | *Not specified*                                                                                                                                              |
| Every event is atomic                       | ✅ [[Events in OCED Core Model#Atomicity\|(Info)]]              | Not specified                                                                      | ✅ [[Events in OCEL2.0#Atomicity\|(Info)]]                      | ✅ [[Events in XES#Atomicity\|(Info)]]                                                         | 〰️ [[Ava; follows mostly OCED#Atomicity\|We also have modelled composite events]]                                                                            |
| Every event has exactly one event type      | ✅ [[Events in OCED Core Model#Event Types\| (Info)]]           | 〰️ [[Events in OCEL1.0#Event Types\|Events have an acitivity]]                     | ✅ [[Events in OCEL2.0#Event Types\|(Info)]]                    | ❌ [[Events in XES#Event Types ~ Event Classifiers --> modeling\|They have event classifiers]] | ✅ [[Ava; follows mostly OCED#Event Types\|We also support relationships between event types]]                                                                |
| Every event carries a timestamp             | ✅ [[Events in OCED Core Model#Time\|(Info)]]                   | ✅ [[Events in OCEL1.0#Time\|(Info)]]                                               | ✅ [[Events in OCEL2.0#Time\|(Info)]]                           | 〰️ [[Events in XES#Time (is an extension, i.e. not required)\|Timestamps are optional]]       | ✅ [[Ava; follows mostly OCED#Time\|Implementation thoughts about resolution, precision and timezones]]                                                       |
| Every event has a unique *event identifier* | ✅ [[Events in OCED Core Model#Uniqueness\|(Info)]]             | 〰️ [[Events in OCEL1.0#Uniqueness + event identifiers\|Events have an identifier]] | ✅ [[Events in OCEL2.0#Uniqueness + event identifiers\|(Info)]] | 〰️ [[Events in XES#Uniqueness + event identifiers\|Identifiers are optional]]                 | TODO                                                                                                                                                         |
| An event may have additional attributes     | ✅ [[Events in OCED Core Model#Event attribute values\|(Info)]] | ✅ [[Events in OCEL1.0#Event attribute values\|(Info)]]                             | ✅ [[Events in OCEL2.0#Event attribute values\|(Info)]]         | ✅ [[Events in XES#Event attribute values\|(Info)]]                                            | ✅ [[Ava; follows mostly OCED#Should all observations of an event be stored with the event?\|Should all observations of an event be stored with the event? ]] |
 

# Definitions
### OCED Core MM

![[Events in OCED Core Model#Definition]]

### OCEL 2.0

![[Events in OCEL2.0#Definition]]

### OCEL 1.0

![[Events in OCEL1.0#Definition]]
### XES

![[Events in XES#Definition]]

