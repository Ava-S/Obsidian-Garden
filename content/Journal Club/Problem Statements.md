## Event abstraction literature
1) [[Event abstraction in process mining, literature review and taxonomy]] (2021) provides a taxonomy of techniques for transforming low-level events into higher-level process concepts. It focuses on abstraction mechanisms but not on a broader conceptual framework for deciding which objects, events, and relationships should exist.
   [Paper](https://link.springer.com/article/10.1007/s41066-020-00226-2)
   
   
   
2) [[Navigating Event Abstraction in Process Mining A Comprehensive Analysis of Sub-problems, Data, and Process Characteristic Considerations]] (2024) provides a more recent synthesis of event abstraction challenges and distinguishes different abstraction problems that arise in practice.
    [Paper](https://link.springer.com/content/pdf/10.1007/978-3-031-50974-2_14.pdf)
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
## Event abstraction in process mining: literature review and taxonomy --> Nice version
Sebastiaan J. van Zelst1,2 • Felix Mannhardt3,4 • Massimiliano de Leoni5 • Agnes Koschmider6

