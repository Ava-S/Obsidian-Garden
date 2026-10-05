Subpage of [[Entities]]
- For entities (both object and events), there is often not a single one-to-one mapping between reality and what has been observed in the data.
- This phenomenon is known as entity resolution in knowledge graphs
  [https://kindatechnical.com/graph-theory-applications/entity-resolution-in-knowledge-graphs.html](https://kindatechnical.com/graph-theory-applications/entity-resolution-in-knowledge-graphs.html)
-
- **Entity resolution in knowledge graphs is the process of figuring out when two different records refer to the same real-world entity and merging into a single canonical node.**
	- Without entity resolution, knowledge graph fills up with duplicates.
- With good entity resolution, every real-world thing has exactly one node, every relationships lands on the right place

## When to do entity resolution?
### Position 1: one real-world thing = one node
- This is a rather philosophical question, but given the number of articles I found on entity resolution and what was told to me during the Neo4j courses, it seems that this is the dominant position .
- If one real world thing is represented by multiple nodes, that the graph no longer faithfully represents the domain, but it represents the observations of the domain.
- Several tooling exists to merge nodes that refer to the same real-world object into a single canonical node.
### Position 2: multiple nodes can represent the same thing

- The graph is modelling observations (not reality itself).
- Use relations in between the observations to indicate they are the same.  This is common is RDF where there are constructs such as owl:sameAs.
### Temporal Entity Resolution
- There's also a thing called temporal entity resolution. ([https://www.tigergraph.com/blog/why-temporal-conflicts-in-entity-resolution-cause-chaos/](https://www.tigergraph.com/blog/why-temporal-conflicts-in-entity-resolution-cause-chaos/))

- Entity resolution answers the practical operational question: Which records represent the same real-world entity right now?
- There's tension between historical and current truth. Both may be accurate in isolation, but the risk emerges when they are treated as equivalent.

# Entity Alignment
- **Entity Resolution / Entity Matching** typically operates over structured or semi-structured records (database tables, web data) and asks: do two records describe the same entity?
- **Entity Alignment** typically operates over knowledge graphs and asks: do two nodes in two different KGs represent the same entity?

See [[Event Resolution]]