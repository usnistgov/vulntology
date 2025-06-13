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

## Example
```json
{
  "Vulnerability": {
    "hasIdentity": [
      {
        "scheme": "http://cve.mitre.org",
        "value": "CVE-2050-1234"
      }
    ],
    "hasOriginatingProduct": {
      "hasProductEnumeration": [
        {
          "scheme": "https://csrc.nist.gov/pubs/ir/7695/final",
          "values": [
            "cpe:2.3:a:fake:fakeproductX:1.0.0:*:*:*:*:*:*:*"
          ]
        }
      ],
      "hasNvdCpeApplicabilityStatement": [
        {
          "nodes": [
            {
              "operator": "OR",
              "negate": false,
              "cpeMatch": [
                {
                  "vulnerable": true,
                  "criteria": "cpe:2.3:a:fake:fakeproductX:1.0.0:*:*:*:*:*:*:*",
                  "matchCriteriaId": "a8928b04-f6c5-46d1-b72a-6c16a4614179"
                }
              ]
            }
          ]
        }
      ]
    },
    "hasScenario": [
      {
        "id": "b4c3887f-28dd-4226-9872-6f44803f1c4b",
        "requiresAttackTheatre": "Remote::Internet",
        "hasExploitedWeakness": [
          "CWE-79"
        ],
        "evidencedBySource": [
          {
            "url": "https://www.acme.com",
            "tag": "vendor-advisory"
          }
        ],
        "affectsProduct": {
          "hasProductEnumeration": [
            {
              "scheme": "https://csrc.nist.gov/pubs/ir/7695/final",
              "values": [
                "cpe:2.3:a:fake:fakeproductX:1.0.0:*:*:*:*:*:*:*"
              ]
            }
          ],
          "hasNvdCpeApplicabilityStatement": [
            {
              "nodes": [
                {
                  "operator": "OR",
                  "negate": false,
                  "cpeMatch": [
                    {
                      "vulnerable": true,
                      "criteria": "cpe:2.3:a:fake:fakeproductX:1.0.0:*:*:*:*:*:*:*",
                      "matchCriteriaId": "a8928b04-f6c5-46d1-b72a-6c16a4614179"
                    }
                  ]
                }
              ]
            }
          ]
        },
        "hasAction": [
          {
            "id": "bd095f8b-b83b-49dc-a2f0-79fd47927147",
            "hasImpactMethod": [
              {
                "hasImpactMethodType": "Code Execution"
              }
            ],
            "affectsContext": "Application::Web Server",
            "hasEntityRole": "Security Authority::Primary",
            "resultsInImpact": [
              {
                "id": "ceb33a58-68cc-4edd-9a5d-0f3c3009ed32",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasPhysicalImpact": "Physical Resource Consumption"
              },
              {
                "id": "17238185-e8ca-4ec7-9db3-bea8b9a2dcde",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasLogicalImpact": "Write Direct",
                "hasLocation": "File System"
              }
            ],
            "doesNotResultInImpact": [
              {
                "id": "25395ff2-19a0-4545-a940-44d0b2a2e0b1",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasLogicalImpact": "Service Interrupt::Hang",
                "hasLocation": "Network Traffic"
              },
              {
                "id": "220d45a1-0086-41c2-b08e-62080a39127d",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasPhysicalImpact": "Human Injury"
              }
            ],
            "name": "vulnEx1_S1_A1"
          },
          {
            "id": "05583e58-eb45-494a-867f-4230e0fa464a",
            "hasImpactMethod": [
              {
                "hasImpactMethodType": "Code Execution"
              }
            ],
            "affectsContext": "Application",
            "hasEntityRole": "Security Authority::Secondary",
            "resultsInImpact": [
              {
                "id": "702f3005-5de6-468f-afd1-c3e338cee6fc",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasLogicalImpact": "Read Direct",
                "hasLocation": "Memory"
              },
              {
                "id": "dc1d7268-2425-4a36-8a81-f80dbbc4d66d",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasPhysicalImpact": "Physical Resource Consumption"
              }
            ],
            "doesNotResultInImpact": [
              {
                "id": "8443ffa0-f0ed-4866-a91d-5d84160973e2",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasLogicalImpact": "Service Interrupt::Hang",
                "hasLocation": "Network Traffic"
              },
              {
                "id": "1456f0a2-46d9-46ca-9189-4f55816e553e",
                "hasCriticality": "Low",
                "hasScope": "Limited",
                "hasPhysicalImpact": "Human Injury"
              }
            ],
            "name": "vulnEx1_S1_A2"
          }
        ],
        "blockedByBarrier": [
          {
            "id": "11741bd2-c5ee-47e8-bd46-ffaf908a5f1c",
            "hasBarrierType": "Authentication/Authorization::Impersonation::Social Engineering",
            "hasEngineeringMethod": [
              "Malicious Link"
            ],
            "hasNeededPrivilege": "User",
            "relatesToContext": "Application"
          }
        ],
        "name": "vulnEx1_S1"
      }
    ],
    "hasSectorOfInterest": [
      "Industrial Control System",
      "Health Care"
    ]
  }
}
```

## Graph View

![Product Graph](/figures/graphsnippets/ProductSnippet.png "Product Graph")
