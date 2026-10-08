## Definition 

> An event observation represents a recording of an event (instance) in a particular source. Multiple event observations may refer to the same event instance. 
## Common sources

Raw records can be interpreted/extracted/discretized into event observations. Below I've added some common sources that contain event observations.
### Event Logs
Every record represents an event observation and contains information from which the event type and timestamp can be determined. A record may contain additional attributes that do not necessarily describe the event itself.


![[Event Log (Data).png]]
**Extract**
- Select the relevant records from the source
- Identify which columns provide event information

**Interpret**
- Interpret e.g. `activity` as the event type
- Interpret e.g. `timestamp` as the event timestamp

**Resolve**
-  Determine which event observations refer to the same underlying event instance.

### Object data (todo better name)
Every record represents an object observation. Object observations may contain information about events involving the observed object, such as timestamps representing observations of operations performed on the object.

Example: timestamp representing when the observed object was opened.
![[Object Data.png|530]]

**Extract**
- Select the relevant records from the source
- Identify which columns provide event information

**Interpret**
- Interpret `Open Time` as an observation of an `ApplicationOpened` event of the observed Application
- Interpret `Close time` as an observation of an `ApplicationClosed` event of the observed Application

**Resolve**
-  Determine which event observations refer to the same underlying event instance.

### Sensor Data
Sensor data describes measurements recorded by sensors. Depending on the format. each record may represent something different. In wide files, each record represents a time point with measurements from multiple sensors. In long files, each records represents a measurement from a single sensor. The sensor variable may be represented in a column, or, when each sensor has its own file, by the file itself.

- Example of a long file where each sensor represents it own file
	![[Croma Sensor Data.png]]

- Example of a wide file![[NXP Sensor Data.png|700]]
**Extract**
- Select sensor data that may contain information about process events

**Discretize**
- Transform measurements into discrete observations that may represent event

**Interpret**
- Assign `Event Type` to the discrete observations
- Interpret e.g. `timestamp` as the event timestamp

**Resolve**
- Determine which event observations refer to the same underlying event instance.

## Distinction from related concepts

| Concept                                       | Difference                                                                                                                                                           |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Concepts/Event Instances\|Event Instances]] | An event instance represents the occurrence, multiple event observations might refer to the same event instance.                                                     |
| Event Resolution                              | Event resolution is the operation of determining which event observations refer to the same event instance.                                                          |
| Event observation                             | An event observation represents a (partial) recording of an event instance in a particular source. Multiple event observations may refer to the same event instance. |
## To-dos
