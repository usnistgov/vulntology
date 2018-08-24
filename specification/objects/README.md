# Vulntology Objects

A Conceptual entity; Objects can be related to other objects, have types, and properties.  Each object, such as [Vulnerability](../objects/vulnerability.md) can have multiple properties and/or relationships with other components. 

Each Object will contain the following sections:

## Description
A short explanation of the object and how it ties into the Vulntology

## Properties
A connection between an object and a value. Properties are inherited by SubTypes of the parent.  Properties are also given an assignment constraint regarding how many values can be associated in the contexxt of a given property. 

## Relationships
A connection relating one object to another. relationships retain an expected cardinality or One to Many or Zero to Many.