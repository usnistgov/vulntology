---
title: "Product"
---

# Product Object

The software and/or hardware configurations that are known to be vulnerable to exploitation of the vulnerability [Scenario](../scenario).  Different Product configurations can be associated with different Scenarios to allow for description of varying impacts and exploitation mechanisms. 

## Properties


An *product* has the following relationships.

### Product Enumeration

{{%usa-tag%}}Name{{%/usa-tag%}} `hasProductEnumeration`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} The enumeration of one or many products as dictated by the identification scheme. Contains a scheme and value pair. This is intended to be used for simple enumerations such as generic free text or common formats that identify explicit instances of products such as CPE or SWID.

### NVD CPE Applicability Statement

{{%usa-tag%}}Name{{%/usa-tag%}} `hasNvdCpeApplicabilityStatement`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} This is to reference the NVD configurations section, which requires much more complex JSON than simple strings.

### CVE v5 Product

{{%usa-tag%}}Name{{%/usa-tag%}} `hasCve5Product`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} This is to reference the CVE Program CVE 5 JSON's product section, which can communicate many complicated methods of string based product applicability.

## Relationships

None.

## Graph View

![Product Graph](/figures/graphsnippets/ProductSnippet.png "Product Graph")