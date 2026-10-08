## Definition 

> A process entity is a distinct element about which process-related information is captured. Process entities can be events, activities or objects, represented either as instances or as types. 

|               | **Event**                                     | **Activity**                                       | **Object**                                      |
| ------------- | --------------------------------------------- | -------------------------------------------------- | ----------------------------------------------- |
| **Instances** | [[Concepts/Event Instances\|Event Instances]] | [[Concepts/Activity Instances\|Activity Instance]] | [[Concepts/Object Instances\|Object Instances]] |
| **Type**      | [[Concepts/Event Type\|Event Type]]           | [[Concepts/Activity Type\|Activity Type]]          | [[Concepts/Object Types\|Object Types]]         |
## Origin
Process entities can be directly observed in source data or derived from available information and domain knowledge through inference, abstraction, enrichment or other forms of processing.  

## Role in the framework

The process entity concept provides an umbrella term for representing and reasoning about different types of entities in process data.
## Distinction from related concepts
## What we concluded
## Evidence / reasoning

- We distinguish between events and activities to better capture that events are atomic observations, while activities don't have to be; Task instances also fall in the category activity. so I'm not sure whether I like the term activity. The terminology is based on [[Exploration/Process Entities/Process Entities#Taxonomy|Taxonomy]]
- We also add objects based on previous experience.
## Open questions
- Is activity the right term?