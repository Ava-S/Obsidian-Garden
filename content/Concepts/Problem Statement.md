
Process mining seeks to improve the understanding of processes that occur in reality through analyzing the data recorded about the process. However, the data available for analysis often does not directly reflect the concepts of the process it represents. In many cases, datasets have a minimal schema, lack contextual information, and are recorded at abstraction levels that do not align with the intended analysis. Consequently, substantial data preparation is required before meaningful process mining analyses can be performed. Despite the importance of this preparation phase, there is currently no widely accepted framework or vocabulary for systematically transforming loosely structured data into semantically rich data structures suitable for process mining. As a result, analysts must determine for themselves what objects, events, relationships and abstraction levels are relevant. These decisions are often implicit or insufficiently documented, making it difficult to assess whether the observed analysis results reflect characteristics of the underlying process or are artefacts of the chosen data representation. This study addresses this gap by proposing a conceptual framework, common vocabulary, and set of operations for constructing well-defined data structures that support process mining analyses while providing a more explicit representation of real-world processes. 


## Event abstraction literature
1) **Event abstraction in process mining: literature review and taxonomy** (van der Aalst et al., 2021) provides a taxonomy of techniques for transforming low-level events into higher-level process concepts. It focuses on abstraction mechanisms but not on a broader conceptual framework for deciding which objects, events, and relationships should exist.[[link.springer.com]](https://link.springer.com/article/10.1007/s41066-020-00226-2)
2) **Navigating Event Abstraction in Process Mining: A Comprehensive Analysis of Sub-problems, Data, and Process Characteristic Considerations** (2024) provides a more recent synthesis of event abstraction challenges and distinguishes different abstraction problems that arise in practice. [[link.springer.com]](https://link.springer.com/content/pdf/10.1007/978-3-031-50974-2_14.pdf)
3) **A framework for understanding event abstraction problem solving: Current states of event abstraction studies** (2024) develops a framework for understanding event abstraction research and its underlying assumptionss. [[sciencedirect.com]](https://www.sciencedirect.com/science/article/pii/S0169023X24000764)
4) **Bridging the Granularity Gap: From Fine-Grained Events to Coarse-Grained Process Models** (2025) explicitly discusses granularity mismatches between recorded data and intended analysis. [[link.springer.com]](https://link.springer.com/content/pdf/10.1007/978-3-032-17618-9_30.pdf)

## Object-centric process mining
- **Object-Centric Event Data: Conceptualization, Extraction and Querying** discusses how object-centric event data can be conceptualized and extracted from raw sources. [[link.springer.com]](https://link.springer.com/content/pdf/10.1007/978-3-032-27997-2_30.pdf)
    
- **OCEL 2.0 Specification** defines a standard metamodel consisting of events, objects, relationships, and attributes. This is likely a key work to position against because your framework appears to operate conceptually before OCEL is instantiated. [[arxiv.org]](https://arxiv.org/html/2403.01975)
    
- **Towards a Simple and Extensible Standard for Object-Centric Event Data (OCED)** analyzes the design space of object-centric event representations and discusses requirements, limitations, and modeling choices. [[arxiv.org]](https://arxiv.org/pdf/2410.14495)
    
- **Object-Centric Event Logs: Specifications, Comparative Analysis and Refinement** compares alternative object-centric data models and discusses what process data should represent. [[arxiv.org]](https://arxiv.org/html/2405.12709v1), [[arxiv.org]](https://arxiv.org/pdf/2405.12709)

## Data preparation and extraction
- **An Event Data Extraction Approach from SAP ERP for Process Mining** argues that ETL is often the most time-consuming step in process mining and presents methods for extracting process data from complex ERP structures. [[arxiv.org]](https://arxiv.org/pdf/2110.03467v1), [[link.springer.com]](https://link.springer.com/chapter/10.1007/978-3-030-98581-3_19)
    
- **Dynamic and Scalable Data Preparation for Object-Centric Process Mining** is probably one of the most important recent papers for your positioning. It explicitly criticizes current approaches to process-data preparation and proposes infrastructure for building object-centric event data pipelines. [[arxiv.org]](https://arxiv.org/html/2410.00596v1), [[arxiv.org]](https://arxiv.org/pdf/2410.00596)

## Process-data quality
- **Process-Data Quality Management Lifecycle: Building Strong Data Foundations for Process Mining** proposes a lifecycle for preparing and assessing process data quality. [[link.springer.com]](https://link.springer.com/content/pdf/10.1007/978-3-032-17618-9_27.pdf)
    
- **A Classification of Data Quality Issues in Object-Centric Event Data** classifies common problems encountered in object-centric process data. [[link.springer.com]](https://link.springer.com/chapter/10.1007/978-3-031-82225-4_23)
    
- **Data Quality in Object-Centric Event Data: Issues Classification and Evaluation** extends this line of research and provides a more mature treatment of object-centric data quality concerns. [[link.springer.com]](https://link.springer.com/article/10.1007/s44311-026-00043-x)

## 5. Granularity and analyst-defined process perspectives

These papers are especially interesting given your focus on representation choices and analysis perspectives.

- **Enriching Object-Centric Event Data with Process Scopes** argues that process boundaries and scopes are analyst-defined rather than objectively present in the data. [[arxiv.org]](https://arxiv.org/pdf/2508.18830v1), [[arxiv.org]](https://arxiv.org/pdf/2508.18830)
    
- **Advancing Object-Centric Process Mining with Multi-Dimensional Data Operations** introduces operations such as roll-up, drill-down, fold, and unfold for changing analysis granularity. [[arxiv.org]](https://arxiv.org/pdf/2412.00393), [[arxiv.org]](https://arxiv.org/html/2412.00393v2)


### Positioning statement
Existing research addresses event abstraction, data quality, event extraction, and object-centric event representations. However, these streams largely assume that analysts already know which objects, events, relationships, and abstraction levels are relevant. There is little support for systematically constructing, documenting, and reasoning about these representation choices. Consequently, the transformation from loosely structured source data to semantically meaningful process representations remains largely ad hoc and implicit.