# Working with healthcare_immunization_registry_api Connector

## Overview

| Operation        | Description |
| ------------- |-------------|
| [AddToImmunizationRegistry](#add-to-immunization-registry)| Registers a newborn child into the national immunization registry for a specific municipality |
| [DeleteImmunizationRecord](#delete-immunization-record)| Deletes an immunization record by its ID for a specific municipality |
| [GetImmunizationRecordById](#get-immunization-record-by-id)| Retrieves a specific immunization record by its unique identifier within a municipality |
| [GetImmunizationRecords](#get-immunization-records)| Retrieves all immunization records for children in a specific municipality |
| [HealthCheck](#health-check)| Returns the health status of the API |

## Operation Details

This section provides details on each of the operations.

### Add To Immunization Registry

Registers a newborn child into the national immunization registry for a specific municipality

**AddToImmunizationRegistry**

```xml
<healthcare_immunization_registry_api.AddToImmunizationRegistry>
    <municipality>{$ctx:municipality}</municipality>
    <childName>{$ctx:childName}</childName>
    <dateOfBirth>{$ctx:dateOfBirth}</dateOfBirth>
    <birthRegistrationNumber>{$ctx:birthRegistrationNumber}</birthRegistrationNumber>
    <vaccines>{$ctx:vaccines}</vaccines>
</healthcare_immunization_registry_api.AddToImmunizationRegistry>
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
### Delete Immunization Record

Deletes an immunization record by its ID for a specific municipality

**DeleteImmunizationRecord**

```xml
<healthcare_immunization_registry_api.DeleteImmunizationRecord>
    <municipality>{$ctx:municipality}</municipality>
    <recordId>{$ctx:recordId}</recordId>
</healthcare_immunization_registry_api.DeleteImmunizationRecord>
```

**Properties**

* municipality: The municipality where the record exists
* recordId: Unique identifier of the immunization record
### Get Immunization Record By Id

Retrieves a specific immunization record by its unique identifier within a municipality

**GetImmunizationRecordById**

```xml
<healthcare_immunization_registry_api.GetImmunizationRecordById>
    <municipality>{$ctx:municipality}</municipality>
    <recordId>{$ctx:recordId}</recordId>
</healthcare_immunization_registry_api.GetImmunizationRecordById>
```

**Properties**

* municipality: The municipality where the record exists
* recordId: Unique identifier of the immunization record
### Get Immunization Records

Retrieves all immunization records for children in a specific municipality

**GetImmunizationRecords**

```xml
<healthcare_immunization_registry_api.GetImmunizationRecords>
    <municipality>{$ctx:municipality}</municipality>
</healthcare_immunization_registry_api.GetImmunizationRecords>
```

**Properties**

* municipality: The municipality to search records for
### Health Check

Returns the health status of the API

**HealthCheck**

```xml
<healthcare_immunization_registry_api.HealthCheck>
</healthcare_immunization_registry_api.HealthCheck>
```

**Properties**

