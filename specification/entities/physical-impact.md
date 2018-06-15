# Physical Impact Entity

Used when exploitation of the Vulnerability could result in a tangible impact to the physical device or machinery controlled by or through the Context, or the surrounding environment, which could be other nearby devices, machinery or people.

## Attributes

### The *physical impact* attribute

**Cardinality**: One or many

#### Valid values

The physical impact attribute value must be one of the following values or sub-values. A sub-value implies the parent value:

- **Property Damage**:  An exploit of the Vulnerability could result in physical damage to the device or surrounding environment.
- **Human Injury**:  An exploit of the Vulnerability could result in injury to users or nearby individuals. Descriptions below are based on Table D.3 in [ISO/IEC 14971:2007].
  - **Negligible**:  Inconvenience or temporary discomfort
  - **Minor**:  Temporary injury or impairment not requiring professional medical intervention
  - **Serious**:  Injury or impairment requiring professional medical intervention
  - **Critical**:  Permanent impairment or life-threatening injury
  - **Catastrophic**:  Death
- **Physical Resource Consumption**:  The Vulnerability allows for consumption of resources outside the digital realm. This consumption could lead to wear and tear on the hardware or financial implications from usage.
  - **Assets**:  Exploitation of the Vulnerability enables excessive use of an asset. The excessive use could decrease the usable lifetime of the asset or unnecessarily consume fuel.
  - **Electricity**:  Exploitation of the Vulnerability enables excessive electricity usage
  - **Water**:  Exploitation of the Vulnerability enables excessive water usage

Data elements:
- value: (required) A unique identifier for the physical impact.

Example:
```
value: Human Injury
value: Catastrophic
```

## Relationships

* Scope:  One and only one Scope value shall be associated with a physical Impact value