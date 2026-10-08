https://opencs.aalto.fi/en/courses/databases/part-8/4-normalization

When a fact is stored in the same place as other other facts that should be independent
--> can lead to insertion, deletion and update anomalies

That why there are functional dependencies: if you know one value, you automatically know the other
	X --> Y
	user_id --> name, email
This can be used as a diagnostic tool for redundancy

Normalization is the process of changing the schema so that every FD is reflected by the structure
if x --> y, then X should be a key (part of a key) of the table that contains Y

Different normalization forms
- 1NF --> each column holds one atomic value (also no duplicated value)
- 2NF --> every non-key column must depend on the whole key, not just an part of it
- 3NF --> avoid transitive dependencies, a non-key column depends on another non-key column
- BCNF --> for every non-trivial functional dependency x--> y, X must be the superkey

Normalization formalizes the rules for tables whose entities are already correctly identifier, it does not, on its own, tell you which entities should exist

Normal forms check structure, not design

Denormalization can also be used as a trade-off
	- Historical snapshots
	- Computed summaries w consistency machinery
	- Cached external data


## Normalizing Property Graphs (https://www.vldb.org/pvldb/vol16/p3031-link.pdf)
- Any mature data model needs to facilitate principles of data integrity
- Since a strong use case of graph data is analytics, the quality of analysis depends fundamentally on the quality of graph data
- This firmly underpins the need to understand sources of data inconsistency and other data quality issues
- Includes the challenge of understanding opportunities for more efficient integrity maintenance and query processing, and database design principles within schema-less graph environments

### Contributions
- Introduce uniqueness constraints and functional dependencies as declarative means to
	- express completeness, integrity and uniqueness requirements in the form of business rules that govern property graph data
	- form the source of redundant property values that drive goals for graph normalization
- Show that graph dependencies facilitate normalization as their implication problem can be captured axiomatically finitely by Horn rules and algorithmically by a linear-time decision algorithm
- Normalize property graphs into lossless dependency-preserving BCNF whenever possible, and guarantee 3NF in general. 
- Demonstrate the extent and benefits of property graph normalization experimentally
### Behavioral Normal Form
[https://doi.org/10.1007/978-3-030-21571-2_1](https://doi.org/10.1007/978-3-030-21571-2_1 "https://doi.org/10.1007/978-3-030-21571-2_1")

### Temporal Normal Form

https://ieeexplore.ieee.org/abstract/document/6065225/

# Why do we need Normalization
- help ensure data consistently represents the objects, events, attributes and relationships in the domain being modelled. 
- Consistent representation of real-world object
	- The same real-world object may appear in multiple records, events or data source --> entity identity and entity resolution
- Correct attribution of attributes
	- An attribute should describe the right object or event, rather than being attached to whichever record happens to contain it. Normalization makes the ownership and scope of attributes explicit. 
	- If multiple attributes are flattened into one record, it becomes easy to confuse their meanings or associate a value with the wrong entity
	--> attribute ownership, semantic consistency and schema design
- Avoid inconsistent duplication --> redundancy and update anomalies
	- Also query efficiency, not needing to query redundant information
- Reliable analysis
	- Redundant information makes analysis more difficult.
- It is also not only about minimizing redundant information --> *explicitly represent what kind of thing each fact is about*

**Normalization helps preserve the semantics of the source domain when constructing an object-centric representation, rather than merely producing a structurally valid event log or graph.**

Different levels of normalization

| Layer                    | Main question                                      | Examples                                                                       |                                                                   |
| ------------------------ | -------------------------------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| Structural normalization | How should facts be organized?                     | Functional dependencies, redundancy, relational normal forms                   |                                                                   |
| Semantic normalization   | What do the facts mean, and what do they describe? | Entity identity, attribute ownership, relationship semantics, schema alignment | Semantic fidelity and reliable integration of object-centric data |
| Temporal normalization   | When are the facts valid, and how do they change?  | Attribute histories, validity intervals, event time versus observation time    |                                                                   |

TO READ
Research on data-aware object-centric event logs identifies the unambiguous association of attributes with events and objects as a prerequisite for reliable analysis
--> https://link.springer.com/chapter/10.1007/978-3-031-27815-0_2
- The previous paragraphs show (without aiming to provide an exhaustive overview) that various contributions made use of attributes that could be stored and used in a flexible manner.
- OCEL observations
	- A: Attributes that are stored in the events table can not unambiguously be linked to an object. 
		- Assumption that attributes that are stored in the events table can only be linked to an event. 
		- Argumentation that evolving attributes have to be stored with events --> and then it is difficult to know to which object it is related
		  **ANSWER:** Should the attributes not be stored with the object instead of abusing the event temporal character?
	- B: it is unclear whether attributes can only be linked to an event or an object individually or whether an attribute can be linked to both an event and an object simultaneously.
	- **ANSWER**: again, evolving attributes need to be stored with the object, the event can be related to the object
	- C: Attributes can only contain exactly one value at a time according to the OCEL metamodel.
		- Each value is treated as a distinct attribute (is not 1NF)
	- D: Both the event and object tables seem to contain a lot of columns that are not always required for each event or object.
- **DOCEL**
	- Static attributes are assumed to be immutable, the **static object attributes** are stored together with the objects themselves, e.g. customer name, product value, fragile and bank account
	- **Dynamic attributes** are assumed to be mutable and its values can change over time. Using two foreign keys (event ID and object ID), the attribute and its value can be traced back to the relevant object as well as the event that created it.
- Attributes can unambiguously be linked to an object, to an event or to both an event and an object with the use of foreign keys. Attributes can have different values over time.
- **Question**: What if the object already has a value before an event is associated to it?


Recent work on object-centric data quality explicitly identifies missing and incorrect event-to-object and object-to-object relationships as object-centric quality problems.
--> https://link.springer.com/article/10.1007/s44311-026-00043-x
- Being the input of Object-Centric Process Mining (OCPM), the quality of the data recorded in OCED logs directly influences the results of the process analysis.
- As with any analysis, the reliability and accuracy of process mining results hinge upon the quality of input data stored in the event logs (Andrews et al. 2020).



--> https://www.sciencedirect.com/science/article/pii/S0306437926000803?via%3Dihub
- The data quality patterns can be addressed by moddeling
	- Object Clones --> entity resolution
	- Dissociative Object (to different real-life objects to which the same object identifier is assigned in the system)
		- Making the column with object IDs a primary key (in case that was not already the case) allows one to find whether the same object ID has been used across different rows, a potential occurrence of dissociative objects. Another way of detecting dissociative objects can be through the use of attribute-based event clustering [86], notably using timestamps and/or activities. By clustering the events that relate to the same object, we can find out if there are two or more disjoint groups of events which could potentially be related to separate (new) objects



