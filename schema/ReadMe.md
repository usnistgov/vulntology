

# JSON Schema Style Guide
All participants providing updates to the JSON schema for the Vulntology should ensure that the following practices are maintained to keep the schema consistent across contributions. 

## General Guidelines:
- All Definitions should be instantiated in capical camel case

``` "SectorOfInterest": ```

- All properties should be in camel case

```"hasEnumeration": ```

- Valid value lists should contain capitalized phrases
``` 
"enum": [       "Malicious Link",
                "Malicious File",
                "Malicious Website Content",
                "Malicious Application"
            ] 
```
- "::" signifies hierarchy in lists
```	
"enum": [
                "Authentication Bypass",
                "Code Execution",
                "Context Escape",
                "Trust Failure",
                "Trust Failure::Failure to Establish Trust",
                "Trust Failure::Failure to Verify Content",
                "Trust Failure::Failure to Verify Receiver",
                "Trust Failure::Failure to Verify Transmitter"
            ]
```