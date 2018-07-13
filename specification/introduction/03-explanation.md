## Vulntology Explanation

### The Components

The vulntology framework is composed of simple components described below:

**Objects**: Conceptual entity contianing properties. Objects can be related to other objects, have types, and properties.

**Types/SubTypes**: A Type is a class of values. Some values within a class may have more specific sets of values which are considered SubTypes.

**Values**: An explicit characteristic used to describe a detail of a Type or SubType.  

**Relationships**: A connection relating one object to another. relationships retain an expected cardinality or One to Many or Zero to Many.

**Properties**: A connection relating a Type to a SubType or an Object to a Type. Properties are inherited by SubTypes of the parent Type. 


### Objects

A list of Objects defined by the Vulntology framework is located under the [objects](../objects) directory. Each object, such as [Vulnerability](../objects/vulnerability.md) can have multiple properties and/or relationships with other components. 

## Values

A list of value sets defined by the Vulntology framework is located under the [values](../values) directory. Values are contained withing Type and SubType classes such as [AttackTheatreType](../values/attack-theater-type.md). 

## Visuals and Examples

### Visuals

To see at a very high level how the Vulntology framework builds on the current methodology of describing vulnerabilities. Refer to the [High Level Model](../figures/high-level-model.pdf). 

To see how all of the components defined in the vulntology relate to eachother please review the [Vunltology Graph](../figures/vulntology-graph.pdf)

### Examples

To assist with understanding how all of the components would work together in a real world application, we have provided a generic Cross Site Scripting vulnerability in graph form. This can be viewed as [XSS Example Graph](../figures/xss-example.pdf).

Additionally, to show how the same information is able to be made human readable please reference the [XSS Example Text](../figures/xss-example-human-text.docx)




