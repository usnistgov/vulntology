---
title: "Scenario"
---

# Scenario Object

A scenario describes the conditions surrounding the possible use of a vulnerability. A Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. Multiple Scenarios can be used to describe these variations. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

## Properties

An *scenario* has the following properties.

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the *scenario*.

The action identifier distinguishes the *scenario* from other *scenarios* related to the same *vulnerability*.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Name

{{%usa-tag%}}Name{{%/usa-tag%}} `hasName`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} A name or label to assist in identifying a given scenario in the context of the containing Vulnerability. This name should be unique across all sibling scenarios.

### Required Attack Theater

{{%usa-tag%}}Name{{%/usa-tag%}} `requiresAttackTheater`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface. (See [Theater](../../values/theater))

### Evidence Source

{{%usa-tag%}}Name{{%/usa-tag%}} `evidencedBySource`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} [Resource Reference](../../values/resource-reference) will assist in proving a Vulnerability Scenario is legitimate.

### Exploited Weakness

{{%usa-tag%}}Name{{%/usa-tag%}} `hasExploitedWeakness`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The weakness causing the Vulnerability. When choosing a value, the most applicable weakness should be selected. (See [Exploited Weakness](../../values/exploited-weakness))

## Relationships

A *scenario* has the following relationships.

### Affected Product

{{%usa-tag%}}Name{{%/usa-tag%}} `affectsProduct`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} [Products](../product) identify the set of products affected within a Scenario.

### Blocked By Barrier

{{%usa-tag%}}Name{{%/usa-tag%}} `blockedByBarrier`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or many
{{%usa-tag%}}Description{{%/usa-tag%}} [Barriers](../barrier) may increase the difficulty of a Scenario.

### Action

{{%usa-tag%}}Name{{%/usa-tag%}} `hasAction`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} [Actions](../action) will occur within a Scenario

## Graph View

![Scenario Graph](/figures/graphsnippets/ScenarioSnippet.png "Scenario Graph")
