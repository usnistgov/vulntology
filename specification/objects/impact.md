# Impact Object

An Impact is a recognized result of an Action for a given Vulnerability Scenario. 

## Properties
- **Scope**:  A coarse measure of the level of impact an exploit could have on a target. (See [Scope](../values/scope.md)) <br />*Each Impact has one Scope.*
- **Criticality**: A measure of the relative importance of the associated Scope. (See [Criticality](../values/criticality.md)) <br />*Each Impact has one Criticality.*

## Types of Impact

- **Logical Impact**: Impacts that occur to the digital aspects of the software. These are considered for assessing traditional notions of confidentiality, integrity and availability.  <br />

    *Type Specific Properties*
  - **hasLogicalImpact**: Impacts that occur to the digital aspects of the software. These are considered for assessing traditional notions of confidentiality, integrity and availability. (See [Logical Impact Types](../values/logical-impact-type.md)  <br />
*Each Logical Impact has One Logical Impact Type resulting from an Action's Impact*
  - **Location**: Designating the specific area or location impacted. Serves as supplemental information (See [Locations](../values/location-type.md)). <br />
  *Each Logical Impact has one or many locations where the impact can occur*

- **Physical Impact**: Impacts that occur the tangible aspects of what the software controls or directly influences. Common examples would be damage to assets, people or loss of resources. <br />

  *Type Specific Properties*
  - **hasPhysicalImpact**: Zero or many Physical Impact Types will result from an Action's Impact (See [Physical Impact Types](../values/physical-impact-type.md) <br />
Each Impact has Zero or many Physical Impact Types will result from an Action's Impact
