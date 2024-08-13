# sample file with a table

Stage | Direct Products | ATP Yields
----: | --------------: | ---------:
Glycolysis | 2 ATP ||
^^ | 2 NADH | 3--5 ATP |
Pyruvaye oxidation | 2 NADH | 5 ATP |
Citric acid cycle | 2 ATP ||
^^ | 6 NADH | 15 ATP |
^^ | 2 FADH2 | 3 ATP |
**30--32** ATP |||
[Net ATP yields per hexose]

# Basic Person with Revisions

Property | Description | Type | Format | Required or Optional | Definition / Comments | IEEE Ontology PURL
-------: | ----------: | ---: | -----: | -------------------: | --------------------: | ------------------:
|id      |Stores the DID of the subject that owns the credential|string|      |required            |Definition: https://www.w3.org/TR/vc-data-model/#identifiers|                  |
|issuanceDate|Issuance date of the credential|string|date-time|required            |                     |                  |
|expirationDate|Expiration date credential|string|date-time|optional            |                     |                  |
|fullName|End-User's full name in displayable form including all name parts, possibly including titles and suffixes, ordered according to the End-User's locale and preferences.|string|      |required            |                     |                  |
|firstName|Current first name(s) or given names of the credential subject|string|      |required            |On certain regions and cultures individuals can have only have one name. In that situation like that the fullName field would be equal to the firstName field.|                  |
|familyName|Current family name(s) of the credential subject|string|      |optional            |                     |                  |
|middleName|Middle name(s) of the End-User. Note that in some cultures, people can have multiple middle names; all can be present, with the names being separated by space characters. Also note that in some cultures, middle names are not used.|string|      |optional            |                     |                  |
|alsoKnownAs|Stage name, religious name or any other type of alias/pseudonym with which a person is known in a specific context besides its legal name. This must be part of the applicable legislation and thus the trust framework (e.g., be an attribute on the identity card).|string|      |optional            |                     |                  |
|dateOfBirth|Date of birth of the credential subject.|string|date-time|required            |                     |                  |
|governmentIdentifier|The unique government or national identifier of the credential subject (constructed by the sending Member State in accordance with the technical specifications for the purposes of cross-border identification and which is as persistent as possible in time).|string|      |required            |                     |                  |
|governmentIdentifierType|Type of government or national identifier, allowed values: passport, national id document, tax id, drivers license, social service number (ssn, social issurance number, or health service id), other.|enumeration|      |required            |                     |                  |
|birthName|Defines the first and the family name(s) of the credential subject at the time of their birth. Structured as a json object with the following 2 fields:|object|      |optional            |                     |                  |
|—firstName|First name(s) or given names of the credential subject at birth.|string|      |optional            |                     |                  |
|—familyName|Family name(s) of the credential subject at birth.|string|      |optional            |                     |                  |
|placeOfBirth|Defines the place where the credential subject is born. The value of this is a JSON object containing some or all of the following fields:|object|      |optional            |                     |                  |
|—locality|Locality: String representing city or locality component.|string|      |optional            |                     |                  |
|—region |region: String representing state, province, prefecture, or region component. This field might be required in some jurisdictions.|string|      |optional            |                     |                  |
|—country|Country: String representing country in ISO 3166-1 alpha-2 codes (e.g. FR, US, CR).|string|      |optional            |                     |                  |
|addresses|Various addresses associated with the credential subject. Structured into the following object:|object|      |optional            |                     |                  |
|—primaryAddress|Primary address of the credential subject.|object|      |optional            |                     |                  |
|——addressLine1|Address Line 1, usually the street address or major indication for the address.|string|      |optional            |                     |                  |
|——addressLine2|Address Line 2, with apartment or suite number or additional indications.|string|      |optional            |                     |                  |
|——locality|locality: String representing city or locality component.|string|      |optional            |                     |                  |
|——region|region: String representing state, province, prefecture, or region component.|string|      |optional            |                     |                  |
|——country|Country: String representing country in ISO 3166-1 alpha-2 codes (e.g. FR, US, CR).|string|      |optional            |                     |                  |
|——postalCode|Postal code (also known as postcode, post code, PIN or ZIP Code).|string|      |optional            |                     |                  |
|gender  |Gender of the credential subject. Some reference values (non-exhaustive list): male, female, transgender male, transgender female, non-binary….|string|      |optional            |                     |                  |
|nationalities|Credential subject’s nationalities.|object|      |optional            |                     |                  |
|—nationality1|Primary nationality of the credential subject using ISO 3166-1 alpha-2 codes (e.g. FR, US, CR).|string|      |optional            |                     |                  |
|email   |End-User's preferred e-mail address. Its value MUST conform to the RFC 5322 [RFC5322] addr-spec syntax.|string|idn-email|optional            |                     |                  |
|emailVerified|True if the End-User's e-mail address has been verified; otherwise false. When this Claim Value is true, this means that the OP took affirmative steps to ensure that this e-mail address was controlled by the End-User at the time the verification was performed. The means by which an e-mail address is verified is context-specific, and dependent upon the trust framework or contractual agreements within which the parties are operating.|boolean|      |optional            |                     |                  |
|phoneNumber|Primary contact number of the user, it should include the country code. The phone number must be formatted according to ITU-T recommendation [E.164], e.g., "1999550123" or "50688785073"|string|      |optional            |                     |                  |
|phoneNumberVerified|True if the End-User's phone number has been verified; otherwise false. When this Claim Value is true, this means that the OP took affirmative steps to ensure that this phone number was controlled by the End-User at the time the verification was performed. The means by which a phone number is verified is context-specific, and dependent upon the trust framework or contractual agreements within which the parties are operating.|boolean|      |optional            |                     |                  |
|customFields|These are custom fields that can be issued by the credential issuer for any other field not accounted in the main schema. 3 string, number, and boolean fields are available.|object|      |optional            |                     |                  |
