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

The Vulntology framework is composed of simple components described below:

- **Objects**: A Conceptual entity; Objects can be related to other objects, have types, relationships, and properties. Each object, such as [Vulnerability](objects/vulnerability), can have multiple properties and/or relationships with other components. 

  - **Relationships**: A connection relating one object to another. Relationships retain an expected cardinality, i.e. or `one to many` or `zero to many`.

  - **Properties**: A connection between an object and a value. Some properties and associated values relate to or drive the use of other properties.

  The top level object to begin with when reviewing the components is the [Vulnerability](objects/vulnerability) object.

- **Values**: An explicit characteristic used to describe a detail of a Type or SubType. A list of value sets defined by the Vulntology framework is located under the [values](values) directory. Values are contained within Type and SubType groups such as [Theatre](values/theater).

  - **Type/SubType**: Types and subtypes are categorizations and/or groupings of values. Subtypes are applicable to a specific value within a parent Type.

## Visuals and Examples

### Visuals

![Vulntology Graph](/figures/vulntology-graph.png "Vultology Graph")

The graph above illustrates how all of the components defined in the Vulntology relate to each other.

To see at a very high level how the Vulntology framework builds on the current methodology of describing vulnerabilities. Refer to the [High Level Model](/about/#high-level-view).

### Examples

To assist with understanding how all of the components would work together in a real world application, we have provided a generic Cross Site Scripting vulnerability in both human readable text and graph form. The human readable text is derived from the graph format data. This displays how human readable descriptions can be derived from a Vulntology representation of a vulnerability. <br />

#### Human Readable Text
---
Legend:<br />
**Object**&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;[**Object Instantiation**]&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;*Property*&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;&nbsp;[*Value*]<br />

There is a **vulnerability**, *known as* [*CVE-2050-1234*].<br />
It is of importance to the [*Industrial Control System*] and [*Health Care*] *sectors*.<br />
The **vulnerability** is due to code that originates from [*Fake FakeProduct 1.0.0.*] <br />
The **vulnerability** [*CVE-2050-1234*] has one **scenario** that is an [*internet*] based [*cross-site scripting*]. <br />
The [**first**] **scenario** is *evidenced by* [*www.acme.com*]<br />
The [**first**] **scenario** *affects product* [*Fake FakeProduct 1.0.0.*] <br />
The [**first**] **scenario** is *blocked by* **social engineering** of an [*application*] [*user*] via a [*malicious link*] and requiring [*user*] [*application*] privileges. <br />
The [**first**] **action** of the [**first**] **scenario** is [*code execution*] to the [*webserver*] which is the [*primary security authority*].<br />
The [**first**] **impact** of the [**first**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct write*].<br />
The [**second**] **action** of the [**first**] **scenario** is [*code execution*] to the [*browser*] which is the [*secondary security authority*].<br />
The [**first**] **impact** of the [**second**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct write*].<br />
The [**second**] **impact** of the [**second**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct read*]. <br />

#### Graph
---
![XSS Example](/figures/xss-example.png "XSS Example")

#### JSON
---
```json
{
    "$schema": "../schema/vulntology-json-schema-1.0-draft.json",
    "vulnerability": {
        "hasIdentity": [
            {
                "scheme": "http://cve.mitre.org",
                "value": "CVE-2050-1234"
            }
        ],
        "hasSectorOfInterest": [
            "Industrial Control System",
            "Health Care"
        ],
        "hasOriginatingProduct": {
            "hasEnumeration": [
                {
                    "scheme": "https://csrc.nist.gov/ns/cpe/2.3",
                    "values": [
                        "cpe:2.3:a:fake:fakeproductX:1.0.0",
                        "cpe:2.3:a:fake:fakeproductY:1.0.0"
                    ]
                },
                {
                    "scheme": "https://nist.gov/cpe/2.2",
                    "values": ["cpe:/a:fake"]
                }
            ],
            "hasCPEApplicabilityStatement": [
                {
                    "operator": "AND",
                    "children": [
                        {
                            "operator": "OR",
                            "cpe_match": [
                                {
                                    "vulnerable": true,
                                    "cpe23Uri": "cpe:2.3:a:fakevendor:fakeproduct:*:*:*:*:*:fake_TSW:*:*",
                                    "versionEndIncluding": "32.0.0.114"
                                },
                                {
                                    "vulnerable": true,
                                    "cpe23Uri": "cpe:2.3:a:fakevendor:fakeproduct:*:*:*:*:*:fake_TSW:*:*",
                                    "versionEndIncluding": "32.0.0.114"
                                }
                            ]
                        },
                        {
                            "operator": "OR",
                            "cpe_match": [
                                {
                                    "vulnerable": false,
                                    "cpe23Uri": "cpe:2.3:o:anotherfakevendor:anotherfakeproduct:*:*:*:*:*:*:*:*"
                                },
                                {
                                    "vulnerable": false,
                                    "cpe23Uri": "cpe:2.3:o:anotherfakevendor:yetanotherfakeproduct:*:*:*:*:*:*:*:*"
                                }
                            ]
                        }
                    ]
                }
            ]
        },
        "hasScenario": [
            {
                "id": "S1",
                "requiresAttackTheatre": "Remote::Internet",
                "hasExploitedWeakness": ["CWE-79"],
                "evidencedBySource": ["https://www.thisisafakeurl.com"],
                "affectsProduct": {
                    "hasEnumeration": [{
                        "scheme": "https://nist.gov/cpe/2.3",
                        "values": ["cpe:2.3:a:fake:fakeproduct:1.0.0"]
                        }],
                    "hasCPEApplicabilityStatement": [
                        {
                            "operator": "AND",
                            "children": [
                                {
                                    "operator": "OR",
                                    "cpe_match": [
                                        {
                                            "vulnerable": true,
                                            "cpe23Uri": "cpe:2.3:a:fakevendor:fakeproduct:*:*:*:*:*:fake_TSW:*:*",
                                            "versionEndIncluding": "32.0.0.114"
                                        },
                                        {
                                            "vulnerable": true,
                                            "cpe23Uri": "cpe:2.3:a:fakevendor:fakeproduct:*:*:*:*:*:fake_TSW:*:*",
                                            "versionEndIncluding": "32.0.0.114"
                                        }
                                    ]
                                },
                                {
                                    "operator": "OR",
                                    "cpe_match": [
                                        {
                                            "vulnerable": false,
                                            "cpe23Uri": "cpe:2.3:o:anotherfakevendor:anotherfakeproduct:*:*:*:*:*:*:*:*"
                                        },
                                        {
                                            "vulnerable": false,
                                            "cpe23Uri": "cpe:2.3:o:anotherfakevendor:yetanotherfakeproduct:*:*:*:*:*:*:*:*"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                "blockedByBarrier": [
                    {
                        "id": "S1B1",
                        "hasBarrierType": "Authentication/Authorization::Impersonation::Social Engineering",
                        "hasEngineeringMethod": ["MaliciousLink"],
                        "neededPrivileges": "User",
                        "relatesToContext": "Application"
                    },
                    {
                        "id": "S1B2",
                        "hasBarrierType": "Authentication/Authorization::Privileges Required",
                        "neededPrivileges": "User",
                        "relatesToContext": "Application"
                    }
                ],
                "hasAction": [
                    {
                        "id": "S1A1",
                        "hasEntityRole": "Security Authority::Primary",
                        "affectsContext": "Application::Web Server",
                        "hasImpactMethod": ["Code Execution"],
                        "resultsInImpact": [
                            {
                                "id": "S1A1I1",
                                "hasLogicalImpact": "Write-Direct",
                                "hasScope": "Limited",
                                "hasCriticality": "Low"
                            }
                        ]
                    },
                    {
                        "id": "S1A2",
                        "hasEntityRole": "Security Authority::Secondary",
                        "affectsContext": "Application",
                        "hasImpactMethod": ["Code Execution"],
                        "resultsInImpact": [
                            {
                                "id": "S1A2I1",
                                "hasLogicalImpact": "Write-Direct",
                                "hasScope": "Limited",
                                "hasCriticality": "Low"
                            },
                            {
                                "id": "S1A2I2",
                                "hasLogicalImpact": "Read-Direct",
                                "hasScope": "Limited",
                                "hasCriticality": "Low",
                                "hasLocation": "Memory"
                            },
                            {
                                "$comment": "This is for testing constraints, and is not for cross-site scripting",
                                "id": "S1A2I3",
                                "hasLogicalImpact": "Privilege Escalation",
                                "hasScope": "Limited",
                                "hasCriticality": "Low",
                                "gainedPrivileges": "Administrator"
                            },
                            {
                                "$comment": "This is for testing constraints, and is not for cross-site scripting",
                                "id": "S1A2I4",
                                "hasPhysicalImpact": "Physical Resource Consumption",
                                "hasScope": "Limited",
                                "hasCriticality": "Low"
                            }
                        ]
                    }
                ]
            }
        ]
    }
}
```
