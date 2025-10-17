### Proof of Age Schema

October 2025 - **Specification Status:** DIF Ratified Specification

JSON Schema: [Proof of Age Schema](https://github.com/decentralized-identity/credential-schemas/tree/main/dif-recommended-schemas/proof-of-age-schema/v1.0)

#### Purpose: 
The objective is to generate a general purpose age schema which should allow for both “age estimation” (several assurance methods to be used) as well as “age verification”.

::: note Proof of Age Non Goals
  The following items are outside the scope of this schema definition:

  - User/holder binding - holder binding is an implementation detail separate from the credential schema standard itself. Device binding is a consideration that implementers should also consider. Several methods can be done to achieve this such as local on device biometrics with secure hardware, or biometric hash data storage in verifiable credentials, periodic biometrics reconfirmation among others)
  - Guardian / parent management - this could be separate VC standard with an associated assurance process
  - Police clearance / Criminal background or similar use cases in child care contexts
:::

![proof of age fields overview diagram](../images/v1.0.0/proof-of-age.png)

#### Proof of Age Abstract Data Model

Main schema for expressing an individual's age. It is composed of a proof of age method field, details on the verification method used, and an age statement field which allows for various schemas for expressing an individual's age. It also includes fields for correctness and level of confidence which are relevant for the age estimation use cases.

For issuance date and expiration date fields please refer to the verifiable credentials data model [version 1.1](https://www.w3.org/TR/vc-data-model/) or [version 2.0](https://www.w3.org/TR/vc-data-model-2.0/) (we assume the usage of these fields).

::: note Proof of Age Required Fields Note
  \* = Required field
:::

| Property                 | Description                                                                                                                                                                                  | Type & Format        | Definition / Comments                                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | -------------------------------------------------------------------------------------------------------------- |
| id  \*                   | Stores the DID of the subject that owns the credential                                                                                                                                       | string               | Definition: https://www.w3.org/TR/vc-data-model-2.0/#identifiers                                               |
| proofOfAgeMethod \*      | Recommended values: "ageEstimation" or "ageVerification"                                                                                                                                     | string / enumeration |                                                                                                                |
| verificationMethod \*    | Verification method used. Recommended values for age verification: document scan, credit card check. Recommended values for age estimation: "facial scan", "voice check", "in person check". | string / enumeration |                                                                                                                |
| ageStatement \*          | Accepted objects: "AgeDate", "AgeBoolean", and "AgeRange".                                                                                                                                   | object               | This could be implemented using the "anyOf" keyword when using json schemas.                                   |
| probabilityOfCorrectness | Probability of correctness of the estimation. Number value between 0 and 100.                                                                                                                | number               |                                                                                                                |
| levelOfConfidence        | Level of confidence with which the verification has been completed allowed values: "asserted", "basic" (90%+), "standard" (99%+), "enhanced" (99.9%+) , and "strict" (99.99%+).              | string / enumeration | Refer to  [IS0/IEC 27566 – Age assurance systems](https://www.iso.org/standard/88143.html) - for more details. |

#### Age Date Object

Object composed of the following fields related to the invidual's birth date: Year, Month,and Day. The schema can represent an age statement in any of the following ways:

- Year only (month and date values are null): e.g. 1952
- Year and month (date value is null) e.g. Sept-1952
- Full date e.g: 25-Sept-1952

::: note Proof of Age Date Object Required Fields
  \* = Required field
:::

| Property | Description                                                                                                          | Type & Format     | Definition / Comments                          |
| -------- | -------------------------------------------------------------------------------------------------------------------- | ----------------- | ---------------------------------------------- |
| type \*  | type of object schema, expected value "AgeDate"                                                                      | string / constant | https://www.w3.org/TR/vc-data-model-2.0/#types |
| year \*  | Numeric value for the individual's birth year e.g 1952.                                                              | integer           |                                                |
| month    | Numeric value for the individual's birth month (Allowed values: 1 to 12). Examples: 9 for September, 10 for October. | integer           |                                                |
| day      | Numeric value for the individual's date of birth during their birth month e.g. 25 for 25-Sept-1952.                  | integer      https://github.com/decentralized-identity/credential-schemas/tree/main/dif-draft-schemas/proof-of-age-schema     |                                                |

#### Boolean Age Statement Object

Object used to express the user is over or under a given age threshold. For example: "over 18", or "under 21". 

::: note Proof of Age Statement Object Required Fields
  \* = Required field
:::

| Property        | Description                                                                                                                                                                                            | Type & Format     | Definition / Comments                          |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- | ---------------------------------------------- |
| type \*         | type of object schema, expected value "AgeBoolean"                                                                                                                                                     | string / constant | https://www.w3.org/TR/vc-data-model-2.0/#types |
| ageOver \*      | Boolean value indicating if the credential holder is older than the value indicated in ageThreshold (if 'true'). Otherwise the credential holder is assumed to be below, i.e. "ageBelow" (if 'false'). | boolean           |                                                |
| ageThreshold \* | Numeric value of the age threshold being expressed (in years).                                                                                                                                         | integer           |                                                |

#### Age Range Statement Object

Object used to indicate a user is in a given in age range for example: between "18 and 25 years of age", or between "40 and 65 years of age". The age values in the range are inclusive of the minimumAge and maximumAge values.
 
 ::: note Proof of Age Range Statement Required Fields
  \* = Required field
:::

| Property   | Description                                      | Type & Format     | Definition / Comments                          |
| ---------- | ------------------------------------------------ | ----------------- | ---------------------------------------------- |
| type \*    | type of object schema, expected value "AgeRange" | string / constant | https://www.w3.org/TR/vc-data-model-2.0/#types |
| minimumAge | Minimum age of the user                          | integer           |                                                |
| maximumAge | Maximum age of the user                          | integer           |                                                |


#### Sample implementations of this schema standard

- DIF: [Proof of Age Schema](https://github.com/decentralized-identity/credential-schemas/tree/main/dif-recommended-schemas/proof-of-age-schema/v1.0)
