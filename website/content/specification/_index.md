---
title: "Specification"
menu:
  primary:
    name: Specification
    weight: 50
sidenav:
  activerenderdepth: 2
---

# The NIST Vulntology Specification

The following and related sections describe the Vulntology specification.

## Conventions Used in this Document

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [BCP 14](https://www.rfc-editor.org/info/bcp14) [RFC2119](https://www.rfc-editor.org/rfc/rfc2119.html) [RFC8174](https://www.rfc-editor.org/rfc/rfc8174.html) when, and only when, they appear in all capitals, as shown here.

## The Components

The vulntology framework is composed of simple components described below:

- **Objects**: A Conceptual entity; Objects can be related to other objects, have types, relationships, and properties. A list of Objects defined by the Vulntology framework is located under the [objects](objects) directory. Each object, such as [Vulnerability](objects/vulnerability), can have multiple properties and/or relationships with other components.

    - **Relationships**: A connection relating one object to another. Relationships retain an expected cardinality, i.e. or `one to many` or `zero to many`.

    - **Properties**: A connection between an object and a value. Some properties and associated values relate to or drive the use of other properties.

    The top level object to begin with when reviewing the components is the [Vulnerability](objects/vulnerability) object.

- **Values**: An explicit characteristic used to describe a detail of a Type or SubType. A list of value sets defined by the Vulntology framework is located under the [values](values) directory. Values are contained within Type and SubType groups such as [Theatre](values/theater).

    - **Type/SubType**: Types and subtypes are categorizations and/or groupings of values. Subtypes are applicable to a specific value within a parent Type.

## Visuals and Examples

### Visuals

To see at a very high level how the Vulntology framework builds on the current methodology of describing vulnerabilities. Refer to the [High Level Model](/about/#high-level-view).

![vulntology-graph](/figures/vulntology-graph.png "Vultology Graph")

The graph above illustrates how all of the components defined in the Vulntology relate to each other.

### Examples

To assist with understanding how all of the components would work together in a real world application, we have provided a generic Cross Site Scripting vulnerability in both graph form and human readable text. The human readable text is derived from the graph format data. To show how both formats are displayed please reference the [XSS Example Text](https://github.com/usnistgov/vulntology/tree/main/examples/xss-example-human-text.md)
