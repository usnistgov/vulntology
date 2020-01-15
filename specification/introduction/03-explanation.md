## Vulntology Explanation

### The Components

The vulntology framework is composed of simple components described below:

**Objects**: A Conceptual entity; Objects can be related to other objects, have types, and properties. A list of Objects defined by the Vulntology framework is located under the [objects](../objects) directory. Each object, such as [Vulnerability](../objects/vulnerability.md) can have multiple properties and/or relationships with other components.

**Type/SubType**: Types and subtypes are categorizations and/or groupings of values. Subtypes are applicable to a specific value within a parent Type.

**Values**: An explicit characteristic used to describe a detail of a Type or SubType. A list of value sets defined by the Vulntology framework is located under the [values](../values) directory. Values are contained within Type and SubType groups such as [Theatre](../values/theater.md).

**Relationships**: A connection relating one object to another. relationships retain an expected cardinality or One to Many or Zero to Many.

**Properties**: A connection between an object and a value or a value to another value. Properties are inherited by SubTypes of the parent.  

## Visuals and Examples

### Visuals

To see at a very high level how the Vulntology framework builds on the current methodology of describing vulnerabilities. Refer to the [High Level Model](../figures/high-level-model.pdf).

![vulntology-graph](../figures/vulntology-graph.png "Vultology Graph")

The graph above illustrates how all of the components defined in the vulntology relate to each other.

### Examples

To assist with understanding how all of the components would work together in a real world application, we have provided a generic Cross Site Scripting vulnerability in both graph form and human readable text. The human readable text is derived from the graph format data. To show how both formats are displayed please reference the [XSS Example Text](../figures/xss-example-human-text.md)
