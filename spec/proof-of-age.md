### Proof of Age Schema

April 2025 - **Specification Status:** editors draft WORK IN PROGRESS

#### Purpose: 
The objective is to generate a general purpose age schema which should allow for both “age estimation” (several assurance methods to be used) as well as “age verification”.

::: note Proof of Age Non Goals
  The following items are outside the scope of this schema definition:

  - User/holder binding - holder binding is an implementation detail separate from the credential schema standard itself. Device binding is a consideration that implementers should also consider. Several methods can be done to achieve this such as local on device biometrics with secure hardware, or biometric hash data storage in verifiable credentials, periodic biometrics reconfirmation among others)
  - Guardian / parent management - this could be separate VC standard with an associated assurance process
  - Police clearance / Criminal background or similar use cases in child care contexts
:::

#### Proof of Age Abstract Data Model

Main schema for expressing an individual's age. It is composed of a proof of age method field, details on the verification method used, and an age statement field which allows for various schemas for expressing an individual's age. It also includes fields for correctness and level of confidence which are relevant for the age estimation use cases.

For issuance date and expiration date fields please refer to the verifiable credentials data model [version 1.1](https://www.w3.org/TR/vc-data-model/) or [version 2.0](https://www.w3.org/TR/vc-data-model-2.0/) (we assume the usage of these fields).

| Property              | Description                                                                                                                                                                    | Type & Format        | Definition / Comments                                        |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|--------------------------------------------------------------|
| id  \*                | Stores the DID of the subject that owns the credential                                                                                                                         | string               | Definition: https://www.w3.org/TR/vc-data-model/#identifiers |
| proofOfAgeMethod \*             | Recommended values: "ageEstimation" or "ageVerification"                                                                                                                        | string / enumeration |                                                              |
| verificationMethod \* | Verification method used. Recommended values for age verification: document scan, credit card check. Recommended values for age estimation: "facial scan", "voice check", "in person check". | string / enumeration |                                                              |
| ageStatement \*   | Accepted schemas: "ProofOfAgeDate", "ProofOfAgeBoolean", and "ProofOfAgeRange".                                                                                          | schema |   This could be implemented using the "anyOf" keyword when using json schemas.               |
| probabilityOfCorrectness | Probability of correctness of the estimation. Number value between 0 and 100.                                                                                                                                                                        | number               |                                                              |
| levelOfConfidence        | Level of confidence with which the verification has been completed allowed values: "asserted", "basic" (90%+), "standard" (99%+), "enhanced" (99.9%+) , and "strict" (99.99%+).  | string / enumeration   |   Refer to  [IS0/IEC 27566 – Age assurance systems](https://www.iso.org/standard/88143.html) - for more details.                    |


::: note Key-on-required-or-optional-for-proof-of-age
  \* = Required field
:::

#### Proof of Age Date Schema

- Schema Type Name: ProofOfAgeDate

Schema composed of 3 fields related to the invidual's birth date: Year, Month,and Day. The schema can represent an age statement in any of the following ways:

- Year only (month and date values are null): e.g. 1952
- Year and month (date value is null) e.g. Sept-1952
- Full date e.g: 25-Sept-1952


| Property  | Description                                                         | Type & Format | Definition / Comments |
|-----------|---------------------------------------------------------------------|---------------|-----------------------|
| year \* | Numeric value for the individual's birth year e.g 1952. | integer       |                       |
| month | Numeric value for the individual's birth month (Allowed values: 1 to 12). Examples: 9 for September, 10 for October. | integer       |                       |
| day | Numeric value for the individual's date of birth during their birth month e.g. 25 for 25-Sept-1952. | integer       |                       |

#### Boolean Age Statement Schema

- Schema Type Name: ProofOfAgeBoolean

Schema composed of 2 fields to express the user is over a given age threshold.

| Property  | Description                                                         | Type & Format | Definition / Comments |
|-----------------|---------------------------------------------------------------------|---------------|-----------------------|
| ageOver \*      | Boolean value indicating if the user is older than the value indicated in ageThreshold | boolean       |                       |
| ageThreshold \* | Numeric value of the age threshold being expressed (in years). | integer       |                       |

#### Age Range Statement Schema

- Schema Type Name: ProofOfAgeRange

Schema composed of 2 fields to indicate a user is in a given in age range for example: between "18 and 25 years of age", or between "40 and 65 years of age".

Schema 

| Property                 | Description                                                                                                                                                                                                                                                                       | Type & Format        | Definition / Comments                  |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|--------------------------------------------------------------|
| minimumAge               | Minimum age of the user                                                                                                                                                                                                                    | integer              |                                                              |
| maximumAge               | Maximum age of the user                                                                                                                                                                                                                    | integer              |                                                              |



#### Credential Issuance Patterns Guidance

::: todo proof of age issuance guidance
  Need to provide guidance on credential issuance for single vs. batch
:::