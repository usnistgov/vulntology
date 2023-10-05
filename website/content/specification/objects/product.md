---
title: "Product"
---

# Product Object

The software and/or hardware configurations that are known to be vulnerable to exploitation of the vulnerability [*scenario*](../scenario).  Different Product configurations can be associated with different *scenarios* to allow for description of varying impacts and exploitation mechanisms.

## Properties

None.

## Relationships

A *product* has the following relationships.

A *product* object MUST include one of the following relationships:

- [`hasProductEnumeration`](#product-enumeration)
- [`hasNvdCpeApplicabilityStatement`](#nvd-cpe-applicability-statement)
- [`hasCve5Product`](#cve-v5-product)

### Product Enumeration

{{%usa-tag%}}Name{{%/usa-tag%}} `hasProductEnumeration`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The enumeration of one or many products as dictated by the identification scheme. Contains an array of `scheme` and `value` pairs.

This is intended to be used for simple enumerations such as generic free text or common formats that identify explicit instances of products such as CPE or SWID.

The `scheme` value MUST be an absolute URI as specified by [RFC 3986 section 4.3](https://www.rfc-editor.org/rfc/rfc3986#section-4.3).

Suggested scheme values include:

- `https://csrc.nist.gov/ns/cpe/2.3`: for a [CPE 2.3 name](https://csrc.nist.gov/pubs/ir/7695/final).

The `value` MUST be based on the lexical space of a string as defined by [ECMA-404 2nd edition, section 9](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf).

### NVD CPE Applicability Statement

{{%usa-tag%}}Name{{%/usa-tag%}} `hasNvdCpeApplicabilityStatement`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} This is to reference the NVD [configurations](https://csrc.nist.gov/schema/nvd/api/2.0/cve_api_json_2.0.schema) section, which requires much more complex JSON than simple strings.

### CVE v5 Product

{{%usa-tag%}}Name{{%/usa-tag%}} `hasCve5Product`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} This is to reference the CVE 5 JSON format's [product](https://github.com/CVEProject/cve-schema/blob/f8f54d50eb22d94447687823c3ef1cbb518e6d86/schema/v5.0/CVE_JSON_5.0_schema.json#L93) section, which can communicate many complicated methods of string based product applicability.

## Graph View

![Product Graph](/figures/graphsnippets/ProductSnippet.png "Product Graph")
