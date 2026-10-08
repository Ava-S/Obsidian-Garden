 (PG keys; [https://dl.acm.org/doi/pdf/10.1145/3448016.3457561](https://dl.acm.org/doi/pdf/10.1145/3448016.3457561))

# Keys in Property Graphs
## Definition

- A graph key is a property or set of properties which help you to identify a node, relationship or property in a graph.
- A key in a property graph database is used to establish and identify unique nodes, edges and properties in the property graph.
- Keys should be applicable to nodes, edges and properties since these all can represent valid real-life entities

## Why Keys

- **Identity Key**: Without an identity key, the resulting property graph could have Customer nodes that appear to be the same when in reality they are not. With an identity key, the integrity of the data is maintained, meaning that there cannot be another Customer node with the customerId.
- To ensure **integrity** when merging/deduplicating data and prevents ill-formed data from entering in the graph.
- Key constraints can also imply participation constraints (e.g. Every Order must have a Customer).
## Purposes
- enforcing data integrity
	- Constrain the database contents
	- Prevent data patterns that are nonsensical, contradictory or unnatural
	- #example a key can be used to prevent a database from storing two copies of information for individuals using the same Serial Service Number
	- #example a key can be used to express participation constraints that restrict the relationships to many-to-many, one-to-many and one-to-one
- allowing the referencing of objects/database entities
	- #example foreign keys in relational databases allow one record to reference another by citing its primary keys
	- In property graphs, relationships are represented with edges rather than foreign keys, and consequently, **keys are not needed for intra-database referencing**.
	- However, **a reference mechanism is still required by external applications** that access the database.
- allowing the identifying of objects
	- A special, but distinct, case of referencing is **when keys are used to identify real-life entities represented by database entities, and vice versa**. Keys specify the identifying information for each object.
	- Particularly relevant in **various entity resolution problems** (TODO: check sources), where it is essential that the identities of entities can be compared through their identifying information.
	- Source 1: Vassilis Christophides, Vasilis Efthymiou, and Kostas Stefanidis. 2015. Entity Resolution in the Web of Data. Morgan & Claypool Publishers.
	- Source 2: Ahmed K. Elmagarmid, Panagiotis G. Ipeirotis, and Vassilios S. Verykios. 2007. Duplicate Record Detection: A Survey. IEEE Trans. Knowl. Data Eng. 19, 1 (2007), 1–16.

Keys are extremely useful in data integration and data migration pipelines




Discussions
- See [[Events and keys]]






Random thoughts
Requirement: coverage: the proposed formalism must address the need to constrain the database and to reference and identify objects.

[https://medium.com/neo4j/graph-data-modeling-keys-a5a5334a1297](https://medium.com/neo4j/graph-data-modeling-keys-a5a5334a1297)