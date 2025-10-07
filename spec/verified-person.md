### Verified Person Schema

August 2025 - **Specification Status:** Working Group Approved

JSON Schema: [Verified Person Schema](https://github.com/decentralized-identity/credential-schemas/tree/main/dif-draft-schemas/verified-person-schema)

#### Purpose: 
The purpose of this credential schema specification is to define the fields required to identify an individual at a basic level for KYC purposes. The schema integrates fields from various standards including: [Open ID Connect](https://openid.net/specs/openid-connect-core-1_0.html) , [Open ID for Identity Assurance](https://openid.net/specs/openid-connect-4-identity-assurance-1_0.html) , [EBSI for natural person](https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/vcdm1.1/multi-uni-pilot/verifiable-attestation-individual-id), and [ISO Mobile Drivers License (ISO/IEC 18013-5:2021)](https://www.iso.org/standard/69084.html). Harmonization and mapping of the fields was done to facilitate interoperability with these standards (see the [mapping section](#mapping-of-the-verified-person-fields-to-various-standards) for details). We also leverage [Schema.org](https://schema.org/Person) as a vocabulary / ontology of terms.

![verified person fields overview diagram](images/verified-person.png)

Use cases: Mainly for financial services, but can also be used in telecommunications, and any sector requiring identity verification for customer onboarding, transaction verification, and regulatory compliance, enabling streamlined and standardized data handling for KYC procedures.

::: note Verified Person Note
  The schema excludes assurance levels and the verification process by which the data was obtained. In addition "trust frameworks" through which the trustworthiness of issuers can be determined are outside the scope of this specification.
:::

For issuance date and expiration date fields please refer to the verifiable credentials data model [version 1.1](https://www.w3.org/TR/vc-data-model/) or [version 2.0](https://www.w3.org/TR/vc-data-model-2.0/) (we assume the usage of these fields).

#### Verified Person Abstract Data Model

::: note verified person note
  \* = Required field
:::

| Property                       | Description                                                                                                                                                                                         | Type & Format      | Definition / Comments                                                                                                               |
| :----------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| id  \*                         | An URI or Decentralized Identifier (DID) of the subject that owns the credential                                                                                                                                              | string             | Definition: https://www.w3.org/TR/vc-data-model/#identifiers                                                                        |
| name (array) *                 | Name(s) of the credential subject including legal name, name at birth (or maiden name), as well as nick names or stage names.                                                                       | Array              | Structured into an array of objects (see the definition of the [Name object](#name-object)   ).                                     |
| birthDate    \*                | Date of birth of the credential subject.                                                                                                                                                            | string / date-time | https://schema.org/birthDate                                                                                                        |
| address (array)                | Various addresses associated with the credential subject.                                                                                                                                           | Array              | Structured into an array of objects (see the definition of the [Address object](#address-object) ).                                 |
| sex                            | Biological sex of the individual at birth. Recommended values: male, female.                                                                                                                        | string             |                                                                                                                                     |
| gender                         | Gender that the credential subject identifies as. Some reference values (non-exhaustive list): male, female, transgender male, transgender female, non-binary….                                     | string             | https://schema.org/gender                                                                                                           |
| nationality  (array)           | Credential subject’s nationality(ies). Expressed as an array of strings of the following:                                                                                                           | Array              |                                                                                                                                     |
^^                               | nationality array items                                                                                                                                                                             | Nationality of the credential subject using ISO 3166-1 alpha-3 codes (e.g. FRA, USA, CRC).                                                      | String |
| contactPoint (array)           | Contact point(s) of the credential subject including emails and phone numbers.                                                                                                                      | Array              | Structured into an array of objects (see the definition of the [Contact Point object](#contact-point-object) ).                     |
| identificationEvidence (array) | Evidence of identifiers of the credential subject including government identifiers.                                                                                                                 | Array              | Structured into an array of objects (see the definition of the [Identification Evidence object](#identification-evidence-object) ). |
| customField (array)            | These are custom fields that can be issued by the credential issuer for any other field not accounted in the main schema. This is a free form array which can be utilized by the credential issuer. | object             | The suggested usage is an array of objects containing "propertyName" and "propertyValue" on each entry.                             |



#### Name Object
The Name Object records the name(s) of the credential subject. The type of name is indicated by the nameType property. There must be at least one entry corresponding to the user's legal name type "legalName". 

::: note name object note
  \* = Required field
:::

| Property        | Description                                                                                                                                                                                                                                                                                                                                                 | Type  & Format       | Definition / Comments                          |
| :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- | :--------------------------------------------- |
| type \*         | Type of name, recommended values: legalName, birthName (names of the credential subject at birth also known as maiden name), alsoKnownAs (Stage name, religious name or any other type of alias/pseudonym with which a person is known in a specific context besides its legal name), otherName. At least one entry for legalName is required at a minimum. | string / enumeration | https://www.w3.org/TR/vc-data-model-2.0/#types |
| givenName       | Given name(s) or First name(s) of the credential subject.                                                                                                                                                                                                                                                                                                   | string               | https://schema.org/givenName                   |
| familyName      | Family name(s) of the credential subject.                                                                                                                                                                                                                                                                                                                   | string               | https://schema.org/familyName                  |
| additionalName  | Middle name(s) of the End-User. Note that in some cultures, people can have multiple middle names; all can be present, with the names being separated by space characters. Also note that in some cultures, middle names are not used.                                                                                                                      | string               | https://schema.org/additionalName              |
| fullName        | End-User's full legal name in displayable form including all name parts, possibly including titles and suffixes, ordered according to the End-User's locale and preferences.                                                                                                                                                                                | string               |                                                |
| honorificPrefix | Title of the credential subject e.g., "Dr." or "Sir"                                                                                                                                                                                                                                                                                                        | string               | https://schema.org/honorificPrefix             |
| salutation      | Salutation of the credential subject e.g., "Mr." or "Miss".                                                                                                                                                                                                                                                                                                 | string               |                                                |
| startDate       | Start date at which this name was first used. This could be used to keep a history of various names used by the credential subject.                                                                                                                                                                                                                         | string / date-time   | https://schema.org/startDate                   |
| endDate         | End date at which this name was used. This could be used to keep a history of various names used by the credential subject.                                                                                                                                                                                                                                 | string / date-time   | https://schema.org/endDate                     |


#### Identification Evidence Object
The Identification Evidence Object records the identifier(s) of the credential subject. The type of identifier is indicated by the identifierType property. The object can record both government and non-government identifiers, however there must be at least one entry corresponding to the credential subject's government identifier, this could be any form of government issued identifier such as passport, national id document, tax id, drivers license, or social service number (ssn, social issurance number, or health service id).
The entry for the government identifier must be the unique government id or national identifier of the credential subject issued by that jurisdiction.

::: note identification evidence object note
  \* = Required field
:::

| Property               | Description                                                                                                                                                                                                                                                                                                                                                                  | Type & Format        | Definition / Comments                          |
| :--------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- | :--------------------------------------------- |
| type   \*              | Type of identifier. For government identifiers the following is a list of recommended values: passport, nationalIdDocument, taxId, driversLicense, socialServiceNumber (ssn, social issurance number, or health service id).  For non-government identifiers some reference values are the following (non-exhaustive list): employeeId, gymMembership, sportsClubMembership. | string / enumeration | https://www.w3.org/TR/vc-data-model-2.0/#types |
| identifier \*          | Identifier value (free form string value).                                                                                                                                                                                                                                                                                                                                   | string               | https://schema.org/identifier                  |
| legalName  \*          | The legal name of the entity that issues the document with the identifier. This could be a government entity such as the drivers license department of a jurisdiction, or the immigration department of a given country. It could also be a non-government entity such as a private university, sports club or gym.                                                           | string               | https://schema.org/legalName                   |
| country                | This is the country of the entity that issues the identifying document. It is a string representing the country in ISO 3166-1 alpha-3 codes (e.g. FRA, USA, CRC).                                                                                                                                                                                                            | string               | https://schema.org/addressCountry              |
| documentExpirationDate | Date in which the document expires or is subject to renewal                                                                                                                                                                                                                                                                                                                  | string / date-time   | https://schema.org/expires                     |


#### Address Object

The Address Object records the address(es) of the credential subject.The type of identifier is indicated by the addressType property.
The object can record a variety of address types, however there must be at least one object entry corresponding to the credential subject's place of birth (identified by the type "placeOfBirth"), the address defines the place where the credential subject is born. For the place of birth, not all fields in the object are required however the country code is mandatory.
This object is an extension of [schema.org/PostalAddress](https://schema.org/PostalAddress), with additional fields for unstructured addresses and start and end dates in order to accommodate for a historical address record.

::: note address object note
  \* = Required field
:::

| Property            | Description                                                                                                                               | Type & Format        | Definition / Comments                          |
| :------------------ | :---------------------------------------------------------------------------------------------------------------------------------------- | :------------------- | :--------------------------------------------- |
| type  \*            | Type of address, recommended values: placeOfBirth, primaryAddress, homeAddress, businessAddress, mailingAddress, previousAddress.         | string / enumeration | https://www.w3.org/TR/vc-data-model-2.0/#types |
| streetAddress       | Usually the street address or major indication for the address.                                                                           | string               | https://schema.org/streetAddress               |
| extendedAddress     | Apartment or suite number or additional indications.                                                                                      | string               | https://schema.org/extendedAddress             |
| locality            | Locality: String representing city or locality component.                                                                                 | string               | https://schema.org/addressLocality             |
| region              | Region: String representing state, province, prefecture, or region component.                                                             | string               |                                                |
| country             | Country: String representing country in ISO 3166-1 alpha-3 codes (e.g. FRA, USA, CRC).                                                    | string               | https://schema.org/addressCountry              |
| postalCode          | Postal code (also known as postcode, post code, PIN or ZIP Code).                                                                         | string               | https://schema.org/postalCode                  |
| unstructuredAddress | Optional one line address field since not all addresses may be structured in the person's KYC source information.                         | string               |                                                |
| startDate           | Start date at which this address was first used. This could be used to keep a history of various addresses used by the credential subject | string / date-time   | https://schema.org/startDate                   |
| endDate             | End date at which this address was last used. This could be used to keep a history of various addresses used by the credential subject    | string / date-time   | https://schema.org/endDate                     |

#### Contact Point Object
The Contact Point Object records the various contact methods of the credential subject (email, phone, others). The type of contact is indicated by the type property. This object is leveraging [schema.org/ContactPoint](https://schema.org/ContactPoint) so any fields in that specification are valid; for simplicity however we are only referencing a subset of the fields in that specification relevant for KYC use cases.

::: note contact point verification
  It is assumed that the credential issuer will have verified that the credential subject is in possession of the contact point(s), the details of how this verification is done are outside the scope of this specification.
:::

::: note contact point object note
  \* = Required field
:::

| Property   | Description                                                                                                                                                                                                                                    | Type  & Format       | Definition / Comments          |
| :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- | :----------------------------- |
| type   \*  | Type of contact point recommended values (non-exhaustive list): personalEmail, workEmail, personalPhone, homePhone, workPhone, otherPhone. It could also include social media or other handles: facebook, linkedIn, x, github, farcaster, etc. | string / enumeration | https://schema.org/contactType |
| email      | Email address, value MUST conform to the RFC 5322 [RFC5322] addr-spec syntax                                                                                                                                                                   | email                | https://schema.org/email       |
| telephone  | Phone number: phone number values must be formatted according to ITU-T recommendation [E.164], e.g., "1999550123" or "50688785073".                                                                                                            | number               | https://schema.org/telephone   |
| url        | URL, used for contact points that refer to websites and similar.                                                                                                                                                      | URL                  | https://schema.org/url         |
| identifier | Identifier used for the contact method (for contact points that are not emails, phone numbers, or URLs).                                                                                                                                       | string               | https://schema.org/identifier  |



#### Mapping of the Verified Person fields to various standards

As explained earlier in the document, this schema credential standard was built by harmonizing various existing individual person identification standards. We now provide details of how the fields of the Verified Person schema maps to these various standards.

##### Mapping to Open ID Connect

Please see below for how the Verified Person maps to the [Open ID Connect](https://openid.net/specs/openid-connect-core-1_0.html) standard.

| Field name in Open ID Connect | Field name in Verified Person | Object in Verified Person                              | Comments                                                                                                        |
| :---------------------------- | :---------------------------- | :----------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------- |
| sub                           | id                            | [Verified Person](verified-person-abstract-data-model) | Subject refers to the DID of the verifiable credential                                                          |
| name                          | fullName                      | [Name](#name-object)                                   |                                                                                                                 |
| given_name                    | givenName                     | [Name](#name-object)                                   |                                                                                                                 |
| family_name                   | familyName                    | [Name](#name-object)                                   |                                                                                                                 |
| middle_name                   | additionalName                | [Name](#name-object)                                   |                                                                                                                 |
| nickname                      | alsoKnownAs                   | [Name](#name-object)                                   |                                                                                                                 |
| preferred_username            | -                             | -                                                      |                                                                                                                 |
| profile                       | -                             | -                                                      |                                                                                                                 |
| picture                       | -                             | -                                                      |                                                                                                                 |
| website                       | -                             | -                                                      |                                                                                                                 |
| email                         | email                         | [Contact Point](#contact-point-object)                 |                                                                                                                 |
| email_verified                | -                             | -                                                      | We assume the credential issuer will have done the required work verify emails of the credential holder.        |
| gender                        | gender                        | [Verified Person](verified-person-abstract-data-model) |                                                                                                                 |
| birthdate                     | birthDate                     | [Verified Person](verified-person-abstract-data-model) |                                                                                                                 |
| zoneinfo                      | -                             | -                                                      |                                                                                                                 |
| locale                        | -                             | -                                                      |                                                                                                                 |
| phone_number                  | telephone                     | [Contact Point](#contact-point-object)                 |                                                                                                                 |
| phone_number_verified         | -                             | -                                                      | We assume the credential issuer will have done the required work verify phone numbers of the credential holder. |
| address                       | Address Object                | [Address](#address-object)                             | The address object provides fields for structured and unstructured addresses.                                   |
| updated_at                    | -                             | -                                                      |                                                                                                                 |

##### Mapping to Open ID for Identity Assurance

Please see below for how the Verified Person maps to the [Open ID Connect for Identity Assurance](https://openid.net/specs/openid-connect-4-identity-assurance-1_0.html) standard.

| Field name in Open ID for Id Assurance | Field name in Verified Person | Object in Verified Person                              | Comments                                                                                                                            |
| :------------------------------------- | :---------------------------- | :----------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| place_of_birth                         | placeOfBirth                  | [Address](#address-object)                             | Can be represented as an address object with type "placeOfBirth".                                                                   |
| country                                | country                       | [Address](#address-object)                             |                                                                                                                                     |
| region                                 | region                        | [Address](#address-object)                             |                                                                                                                                     |
| locality                               | locality                      | [Address](#address-object)                             |                                                                                                                                     |
| nationalities                          | nationality                   | [Verified Person](verified-person-abstract-data-model) | The nationality array object in the verified person object contains an array of country codes for the nationalities of the subject. |
| birth_family_name                      | familyName                    | [Name](#name-object)                                   |                                                                                                                                     |
| birth_given_name                       | givenName                     | [Name](#name-object)                                   |                                                                                                                                     |
| birth_middle_name                      | additionalName                | [Name](#name-object)                                   |                                                                                                                                     |
| salutation                             | salutation                    | [Name](#name-object)                                   |                                                                                                                                     |
| title                                  | honorificPrefix               | [Name](#name-object)                                   |                                                                                                                                     |
| msisdn                                 | telephone                     | [Contact Point](#contact-point-object)                 | Can be represented as an contact point object with type "personalPhone".                                                            |
| also_known_as                          | alsoKnownAs                   | [Name](#name-object)                                   |                                                                                                                                     |

##### Mapping to EBSI for Natural Person

Please see below for how the Verified Person maps to the [EBSI for Natural Person](https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/vcdm1.1/multi-uni-pilot/verifiable-attestation-individual-id) standard.

| Field name in EBSI Natural Person | Field name in Verified Person | Object in Verified Person | Comments                                                                      |
| :-------------------------------- | :---------------------------- | :------------------------ | :---------------------------------------------------------------------------- |
| id                                | id                            | [Verified Person](verified-person-abstract-data-model)           |                                                                               |
| familyName                        | familyName                    | [Name](#name-object)                      |                                                                               |
| firstName                         | givenName                     | [Name](#name-object)                      |                                                                               |
| dateOfBirth                       | birthDate                     | [Verified Person](verified-person-abstract-data-model)           |                                                                               |
| personalIdentifier                | identifier                    | [Identification Evidence](#identification-evidence-object)   |                                                                               |
| nameAndFamilyNameAtBirth          | fullName                      | [Name](#name-object)                      | Can be represented as a name object with type "birthName".                    |
| placeOfBirth                      | placeOfBirth                  | [Address](#address-object)                   | Can be represented as an address object with type "placeOfBirth".             |
| currentAddress                    | Address Object                | [Address](#address-object)            | Can be represented as an address object with type "primaryAddress" or "homeAddress". |
| gender                            | gender                        | [Verified Person](verified-person-abstract-data-model)           |                                                                               |

##### Mapping to ISO Mobile Drivers License

Please see below for how the Verified Person maps to the [ISO Mobile Drivers License (ISO/IEC 18013-5:2021)](https://www.iso.org/standard/69084.html) standard.

| Field name in ISO MDL          | Field name in Verified Person | Object in Verified Person                                  | Comments                                                                                                                        |
| :----------------------------- | :---------------------------- | :--------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------ |
| family_name                    | familyName                    | [Name](#name-object)                                       |                                                                                                                                 |
| given_name                     | givenName                     | [Name](#name-object)                                       |                                                                                                                                 |
| birth_date                     | birthDate                     | [Verified Person](verified-person-abstract-data-model)     |                                                                                                                                 |
| issue_date                     | -                             | -                                                          |                                                                                                                                 |
| expiry_date                    | documentExpirationDate        | [Identification Evidence](#identification-evidence-object) |                                                                                                                                 |
| issuing_country                | country                       | [Identification Evidence](#identification-evidence-object) |                                                                                                                                 |
| issuing_authority              | legalName                     | [Identification Evidence](#identification-evidence-object) | Legal name of the entity that issues the credential.                                                                            |
| document_  number              | identifier                    | [Identification Evidence](#identification-evidence-object) |                                                                                                                                 |
| portrait                       | -                             | -                                                          |                                                                                                                                 |
| driving_privileges             | -                             | -                                                          |                                                                                                                                 |
| un_distinguishing_sign         | country                       | [Identification Evidence](#identification-evidence-object) | Whilst not an exact match, this could be matched to 3 letter iso country code used in the identification evidence object.       |
| administrative_number          | -                             | -                                                          |                                                                                                                                 |
| sex                            | sex                           | [Verified Person](verified-person-abstract-data-model)     |                                                                                                                                 |
| height                         | -                             | -                                                          |                                                                                                                                 |
| weight                         | -                             | -                                                          |                                                                                                                                 |
| eye_color                      | -                             | -                                                          |                                                                                                                                 |
| hair_color                     | -                             | -                                                          |                                                                                                                                 |
| birth_place                    | placeOfBirth                  | [Address](#address-object)                                 | Can be represented as an address object with type "placeOfBirth".                                                               |
| resident_address               | Address Object                | [Address](#address-object)                                 | Can be represented as an address object with type "primaryAddress" or "homeAddress".                                            |
| portrait_capture_date          | -                             | -                                                          |                                                                                                                                 |
| age_in_years                   | -                             | -                                                          |                                                                                                                                 |
| age_birth_ year                |                               |                                                            |                                                                                                                                 |
| age_over_NN                    | -                             | -                                                          |                                                                                                                                 |
| issuing_jurisdiction           | -                             | -                                                          |                                                                                                                                 |
| nationality                    | nationality                   | [Verified Person](verified-person-abstract-data-model)     | Nationality array object in the verified person object contains an array of country codes for the nationalities of the subject. |
| resident_city                  | locality                      | [Address](#address-object)                                 | Can be represented as an address object with type "primaryAddress" or "homeAddress"; and then use the locality field.           |
| resident_state                 | region                        | [Address](#address-object)                                 | Can be represented as an address object with type "primaryAddress" or "homeAddress"; and then use the region field.             |
| resident_postal_code           | postalCode                    | [Address](#address-object)                                 | Can be represented as an address object with type "primaryAddress" or "homeAddress"; and then use the postalCode field.         |
| biometric_template_xx          | -                             | -                                                          |                                                                                                                                 |
| family_name_national_character | familyName                    | [Name](#name-object)                                       | There is no restriction on using Latin only characters for names. This is an implementer's decision.                            |
| given_name_national_character  | givenName                     | [Name](#name-object)                                       | There is no restriction on using Latin only characters for names. This is an implementer's decision.                            |
| signature_ usual_mark          | -                             | -                                                          |                                                                                                                                 |
| online_token_xxxx              | -                             | -                                                          |                                                                                                                                 |
| online_url_xxxx                | -                             | -                                                          |                                                                                                                                 |

#### Sample implementations of this schema standard

- DIF: [Verified Person Schema](https://github.com/decentralized-identity/credential-schemas/tree/main/dif-draft-schemas/basic-person-schema)
- Privado ID (JSON-LD): [basic person](https://tools.privado.id/schemas/a6405ff0-ed9e-4bfb-bf75-6045aa4acd20)
- Oasis [Lightweight Verifiable Credential Schema & Process](https://docs.oasis-open.org/lvcsp/lvcs/v1.0/cs01/lvcs-v1.0-cs01.pdf)
