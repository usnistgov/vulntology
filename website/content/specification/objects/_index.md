---
title: "Objects"
sidenav:
  focusrenderdepth: -1
---
# Vulntology Objects

A Conceptual entity in the vulntology.

Objects can be related to other objects, have types, and properties.  Each object, such as [vulnerability](vulnerability), can have multiple properties and/or relationships with other components.

## Object Types

The following objects are defined by the Vulntology.

- [action](action)
- [barrier](barrier)
- [impact](impact)
- [impact method](impact-method)
- [product](product)
- [scenario](scenario)
- [vulnerability identifier](vulnerability-identifier)
- [vulnerability](vulnerability)

## Object Notation

Each Object will contain the following sections:

### Description

A short explanation of the object and how it ties into the Vulntology.

### Properties

A connection between an object and a value. Properties are inherited by SubTypes of the parent.  Properties are also given an assignment constraint regarding how many values can be associated in the context of a given property.

### Relationships

A connection relating one object to another. relationships retain an expected cardinality of `one to many` or `zero to many`.
