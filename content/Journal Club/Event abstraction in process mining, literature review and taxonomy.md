### Core Problem
The majority of the available process mining techniques assume that event data are captured on the same level of granularity. However, often, multiple dedicated information systems are used within a company that support different aspects of the business, e.g., customer relationship
management (CRM), enterprise resource planning (ERP), etc. Typically, these systems track the different activities executed, i.e., events, in the context of the process. However, these systems capture the concept of activities (and hence events) differently, which might not all be at the
same level of abstraction, i.e., the level of granularity might be too fine. Also, different systems within the same organization might not agree on their granularity level, i.e., joining the event data requires us to first ensure the same granularity. [...]

### Consequence
The presence of mixed/overly fine granularity in event logging causes problems in the direct application of process mining techniques. For example, in the context of process discovery, the presence of events in the data leads to the discovery of process models that are often of high complexity, i.e., no longer human interpretable. [...] As a naive solution, one might be tempted to just focus on the most frequent events, independently of the granularity. However, this typically leads to process models that are severely under-fitting with respect to the data. Hence, we advocate the need of more advanced ways of abstracting fine-granular events into higher level concepts.

### Research Gap
`Shifts from the practical problem to the literature gap`

In process mining, a large share of research has already been conducted on the problem of event log abstraction. However, a concise overview and categorization of these works is lacking. Hence, in this paper, we present a literature survey of event abstraction techniques developed in the context of process mining. We rely on a taxonomy, derived from the existing literature, to provide an overview of event abstraction techniques, which additionally allows us to identify interesting directions for future work.