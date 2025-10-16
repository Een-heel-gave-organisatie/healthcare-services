# Working with healthcare_immunization_registry_api Connector

## Overview

| Operation        | Description |
| ------------- |-------------|
| [DELETE_healthcare_{municipality}_immunization_records_{recordId}](#delete-healthcare-{-municipality-}-immunization-records-{-record-id-})| Deletes an immunization record by its ID for a specific municipality |
| [GET_health](#get-health)| Returns the health status of the API |
| [GET_healthcare_{municipality}_immunization_records](#get-healthcare-{-municipality-}-immunization-records)| Retrieves all immunization records for children in a specific municipality |
| [GET_healthcare_{municipality}_immunization_records_{recordId}](#get-healthcare-{-municipality-}-immunization-records-{-record-id-})| Retrieves a specific immunization record by its unique identifier within a municipality |
| [POST_healthcare_{municipality}_immunization_register](#post-healthcare-{-municipality-}-immunization-register)| Registers a newborn child into the national immunization registry for a specific municipality |

## Operation Details

This section provides details on each of the operations.

### DELETE healthcare { municipality } immunization records { record Id }

Deletes an immunization record by its ID for a specific municipality

**DELETE_healthcare_{municipality}_immunization_records_{recordId}**

```xml
<healthcare_immunization_registry_api.DELETE_healthcare_{municipality}_immunization_records_{recordId}>
    <municipality>{$ctx:municipality}</municipality>
    <recordId>{$ctx:recordId}</recordId>
</healthcare_immunization_registry_api.DELETE_healthcare_{municipality}_immunization_records_{recordId}>
```

**Properties**

* municipality: The municipality where the record exists
* recordId: Unique identifier of the immunization record
### GET health

Returns the health status of the API

**GET_health**

```xml
<healthcare_immunization_registry_api.GET_health>
</healthcare_immunization_registry_api.GET_health>
```

**Properties**

### GET healthcare { municipality } immunization records

Retrieves all immunization records for children in a specific municipality

**GET_healthcare_{municipality}_immunization_records**

```xml
<healthcare_immunization_registry_api.GET_healthcare_{municipality}_immunization_records>
    <municipality>{$ctx:municipality}</municipality>
</healthcare_immunization_registry_api.GET_healthcare_{municipality}_immunization_records>
```

**Properties**

* municipality: The municipality to search records for
### GET healthcare { municipality } immunization records { record Id }

Retrieves a specific immunization record by its unique identifier within a municipality

**GET_healthcare_{municipality}_immunization_records_{recordId}**

```xml
<healthcare_immunization_registry_api.GET_healthcare_{municipality}_immunization_records_{recordId}>
    <municipality>{$ctx:municipality}</municipality>
    <recordId>{$ctx:recordId}</recordId>
</healthcare_immunization_registry_api.GET_healthcare_{municipality}_immunization_records_{recordId}>
```

**Properties**

* municipality: The municipality where the record exists
* recordId: Unique identifier of the immunization record
### POST healthcare { municipality } immunization register

Registers a newborn child into the national immunization registry for a specific municipality

**POST_healthcare_{municipality}_immunization_register**

```xml
<healthcare_immunization_registry_api.POST_healthcare_{municipality}_immunization_register>
    <municipality>{$ctx:municipality}</municipality>
    <childName>{$ctx:childName}</childName>
    <dateOfBirth>{$ctx:dateOfBirth}</dateOfBirth>
    <birthRegistrationNumber>{$ctx:birthRegistrationNumber}</birthRegistrationNumber>
    <vaccines>{$ctx:vaccines}</vaccines>
</healthcare_immunization_registry_api.POST_healthcare_{municipality}_immunization_register>
```

**Properties**

* municipality: The municipality where the child is being registered
* childName: Full name of the child Type: string
* dateOfBirth: Date of birth in YYYY-MM-DD format Type: string
* birthRegistrationNumber: Official birth registration number from civil registry Type: string
* vaccines: Array of vaccines administered Type: array
This is parameter is of a complex type. Use the below schema to build the parameter and set it as a property to this
parameter.
```json
{
  "type" : "array",
  "description" : "Array of vaccines administered",
  "items" : {
    "type" : "object",
    "properties" : {
      "vaccineName" : {
        "type" : "string",
        "example" : "Hepatitis B"
      },
      "dateAdministered" : {
        "type" : "string",
        "format" : "date",
        "example" : "2024-01-15"
      },
      "batchNumber" : {
        "type" : "string",
        "example" : "HB-2024-001"
      }
    }
  }
}
```
