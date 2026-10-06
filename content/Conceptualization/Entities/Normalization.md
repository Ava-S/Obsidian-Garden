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

Recent work on object-centric data quality explicitly identifies missing and incorrect event-to-object and object-to-object relationships as object-centric quality problems.
--> https://link.springer.com/article/10.1007/s44311-026-00043-x
--> https://www.sciencedirect.com/science/article/pii/S0306437926000803?via%3Dihub



