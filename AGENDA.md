# credential-schemas - rolling agenda & minutes

[![hackmd-github-sync-badge](https://hackmd.io/fcNWJ_efTWaYZGpWXxeZxA/badge)](https://hackmd.io/fcNWJ_efTWaYZGpWXxeZxA)

[**WG projects** ](https://github.com/decentralized-identity?q=wg-cc&type=&language=) | [ DIF page ](https://identity.foundation/working-groups/claims-credentials.html) | [Mailing list and Wiki ](https://lists.identity.foundation/g/cc-wg) | [Meeting recordings](https://docs.google.com/spreadsheets/d/1wgccmMvIImx30qVE9GhRKWWv3vmL2ZyUauuKx3IfRmA/edit#gid=1252135265)

_For this call, you are encouraged to turn your video on. This is a good way to build rapport given we are a large, disparate group experiencing a lot of churn._

_This document is live-edited DURING each call, and stable/authoritative copies live on our github repo under /agenda.md .
Please note that we might not notice a pullrequest in time, but you are free to propose agenda items for future meetings via hackmd._

<details>
<summary> Meeting information </summary>

- Before you contribute - [**join DIF**](https://identity.foundation/join) and [sign the WG charter](https://bit.ly/DIF-WG-select1) (both are required!)
- Time: TODO
- [Calendar entry](https://calendar.google.com/event?action=TEMPLATE&tmeid=NnBnMW43NmRib3YwNDI3dXA5ZW8xOHVlbjZfMjAyMDExMDNUMjAwMDAwWiBkZWNlbnRyYWxpemVkLmlkZW50aXR5QG0&tmsrc=decentralized.identity%40gmail.com&scp=ALL)
- [Zoom room]()
</details>

#### Future topics:

<details>
<summary> Topics for upcoming meetings</summary>

- Community Credential contributions to repo (to be discussed on 4-March)
- Credential schema online platform
- AML credential schema
- topic n. (tbd)

</details>


## Meeting - 11 February 2025 - (1300 ET)

Attendees: Otto Mora, Valerio Camaiani, Don Sheppard, Adrian Field

1. Welcome and agenda review
2. Discussion of "Proof of Age" Schema - (Otto)
    - Debrief on the session
    - Update on Proof of Age Draft Schema (work in progress by Otto)
    - Discussion of various ways of proving age by Adrian, Otto, Valerio, and Don: Exact age, Boolean "age over", partial (year only or year and month only), age range.
3. Other items


## Meeting - 28 January 2025 - (1300 ET)

- Workshop on Proof of Age no meeting this week.


## Meeting - 14 January 2025 - (1300 ET)

Attendees: Otto Mora, Valerio Camaiani, Don Sheppard, Kim Duffy

1. Welcome and agenda review
2. Discussion of Proof of Age Proposal and session in January to begin standardization process - (Otto)
    - Update on out-reach / promotion
    - Invitation sent to w3c ccg
    - Privado ID will promote the event with a blog post - will be published this week
    - Updates on potential participants
3. Other items: Discussion on JWT

## Meeting - 31 December 2024 - (1300 ET)

Attendees: Otto Mora, Valerio Camaiani, Don Sheppard, Kim Duffy

1. Working session for the DIF Proof of Age Schema Webinar:
    - Discussion of Proof of Age Schema Working Session
    - Public working session scheduled for 28-January to begin standardization process
    - Privado ID will promote the event with a blog post
    - Discussion on out-reach and potential participants to invite

## Meeting - 3 December 2024 - (1300 ET)

Attendees: Otto Mora, Valerio Camaiani, Don Sheppard, Kim Duffy

1. Welcome and agenda review
2. Discussion of Proof of Age Proposal and session in January to begin standardization process - (Otto)
    - Decision on exact date on which to hold the event: 28-Jan
3. Discussion on the "basic person schema" for KYC (Otto)
    - Review feedback from W3C / Manu on field naming convention - https://github.com/decentralized-identity/credential-schemas/issues/23
    - Review feedback from Manu regarding the identifierType: https://github.com/decentralized-identity/credential-schemas/issues/24


## Meeting - 19 November 2024 - (1300 ET)

Attendees: Otto Mora, Valerio Camaiani, Don Sheppard, Kim Duffy

1. Welcome and agenda review
2. Intro to Don Sheppard (new working group member from OASIS Light Weight Credentials Framework) discussion of collaboration between Oasis and DIF on the "basic person schema"
 - Feedback regarding IANA attributes
3. Discussion of Proof of Age Proposal and session in January to begin standardization process - (Otto)
    - Feedback received at IIW, do we need to do special accommodations for the "single use" proof of age burner credentials, example provided from the TrueAge specification in California
    - Proposal to add additional age verification method: "credit card check" based on feedback that [Mastercard provides age verification in 3D Secure](https://www.biometricupdate.com/202410/mastercard-launches-identity-attribute-verification-based-on-payment-card-data)
4. Other Items: Co-Chair update (Jim S. leaving the group for now)

## Meeting - 5 November 2024 - (1300 ET)

Attendees: Otto Mora, Kim Duffy, Adrian Field

1. Welcome and agenda review
2. Discussion of [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema): (Otto)
    - Migrated the place of birth date to the addresses array
    - Fixed phone number field note
    - Clarified name of object items
    - Added nameToDate and addressToDate field to keep history of names
    - Minor wording clarifications
3. Debrief of Proof of Personhood discussion at IIW and W3C CCG (Kim)
4. Proof of Age proposal, feedback received at IIW (Otto)
5. Updates of "basic person schema" after IIW (Otto) 




## Meeting - 22 October 2024 - (1300 ET)

Attendees: Otto Mora, Kim Duffy, Adrian Field, Filippos Lymperopoulos

1. Welcome and agenda review
2. Discussion of [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema) Final review before initial draft is presented at IIW: (Otto)
    - Implemented the names object
    - Added the address and name from dates fields
    - Added "previousAddress" type
    - Removed "email and phone verified fields"
    - Split the name and salutation
    - Implemented the contact channels object
    - Moved the government identifiers to the identifiers object
    - Enumerations can be customized for specific use cases
    - Additional feedback received from Adrian Field
3. Discussion Additional IIW Sessions we could hold such as Proof of Age:
    - Agreed to hold a session on a Proof of Age schema that supports both Age Verification and Age Estimation
4. Discussion around credential schema discovery process (Filippos)
   - Agreed to mention this during the IIW sessions
5. Brief discussion around a future "assurance wrapper" for the basic person schema (Adrian)


## Meeting - 8 October 2024 - (1300 ET)

Attendees: Otto Mora, Kim Duffy, Valerio Massimo Camaiani, Filippos Lymperopoulos

1. Welcome and agenda review
2. Discussion of [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema): (Otto)
    - Agreed to proposal from Mike Parhill for fields with enumerations
    - Agreed to split name attributes into sub-table as proposed by Adrian Field
3. Began discussion on Proof of Age with example from the Privado ID schema explorer, and potential connection with the Proof of Personhood work
4. Schema Discovery Process:
   - Quick discussion on PRs contributed by Valerio and Filipos
   - Agreed to use tags for categorization of schemas
   - Discussion on potentially using the schemas repo for the DIF Hackathon

## Meeting - 10 September 2024 - (1300 ET)

Attendees: Otto Mora, Adrian Field

1. Welcome and agenda review
3. Review of [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema): (Otto and Adrian Field)
    - Feedback from Adrian on various field names and structure of the names section
    - Suggestions from Adrian on how to structure the spec
    - Review of mapping of the basic person to Open ID connect core, Open ID for ID assurance, and ISO mdl
    - Decision to split the salutation and title into separate fields
    - Accepted suggestion on "Name from Date" and "Address from Date"
    - Agreed to remove "email verified" and "phone number verified" fields, as KYC issuer would confirm this data
    - Agreed to correct enumeration fields for "nameType" and a few others that do no


## Meeting - 27 August 2024 - (1300 ET)

Attendees: Jim Schoening, Otto Mora, Kim Duffy, Adrian Field, Valerio Massimo Camaiani, Filippos Lymperopoulos, Moises Jaramillo, Christopher Wilson (Guest)

1. Welcome and agenda review
2. Brief update on [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema): (Otto)
    - Attributes have been split into sub-tables
    - Decided on ISO 3 letter codes after working group vote
    - Feedback from Adrian Field regarding the need for an unstructured address field
3. Reviewed updated presentation on [credential schemas discovery process](https://docs.google.com/presentation/d/1wksGUmAoN4jq36pyfhuMW6SZijujCzmY/edit?usp=sharing&ouid=112319009131764791841&rtpof=true&sd=true) - (Filipos)
 - Discussed categorization proposal
 - Positive feedback received from Kim Duffy
4. Conversation with My Data Global on "Data Models" - Christopher Wilson and Jim Schoening


## Meeting - 13 August 2024 - (1300 ET)

Attendees: Jim Schoening, Otto Mora, Kim Duffy, Adrian Field, Valerio Massimo Camaiani, Filippos Lymperopoulos, Steven Frank (Switchchord),

1. Welcome and agenda review
2. Debrief on "schema selector" presentation for Veramo (Jim Schoening)
3. Presentation on potential [credential schemas discovery process](https://docs.google.com/presentation/d/1wksGUmAoN4jq36pyfhuMW6SZijujCzmY/edit?usp=sharing&ouid=112319009131764791841&rtpof=true&sd=true)
4. Brief update on [basic identity schema](https://identity.foundation/credential-schemas/#basic-person-schema):
    - Work in progress currently on the spec-up (Otto)
    - Feedback regarding [EIDAS catalogue of attributes](https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/14402-European-digital-identity-framework-verification-of-electronic-attestation-of-attributes_en)
6. Others

## Meeting - 30 July 2024 - (1300 ET)

Attendees: Jim Schoening, Otto Mora, Kim Duffy Adrian Field, Valerio Massimo Camaiani, Filippos Lymperopoulos, Steven Frank (Switchchord),

1. Welcome and agenda review
2. Reviewed basic identity schema, and feedback from Adrian Field from One ID
    - Decided to call it the "Basic Person Schema"
    - Feedback regarding various attributes including addressess, date of birth, and government identifier
    - Decided to place address in an array object
    - Discussed ISO 2 letter codes vs. 3 letter codes
4. Reviewed "schema selector" presentation for Veramo (Jim Schoening)
4. Reviewed suggestions from Crossmint team regarding a potential credential schemas directory
5. 5. Others

## Meeting - 16 July 2024 - (1300 ET)

Attendees: Jim Schoening, Otto Mora, Kim Duffy, Valerio Massimo Camaiani, Alfonso Gomez Jordana Manas, Cole Davis, Steven Frank (Switchchord)

1. Welcome and introductions
2. Administrivia
3. Review [current unified glossary](https://docs.google.com/spreadsheets/d/12B6oXYOfOB8ocyZvsehDIT4D5ZjMNn9z/edit?gid=1811559849#gid=1811559849) and next steps
4. Discussion
    - Steven Frank:
       - buzzsaw is why they should do it
       - are we developing just the credential schema, or the mechanism for verifying the identity
       - talk with groups PIPL; Steven to make introductions
     - Otto presented merged view - will send this out for feedback. Will focus on Basic KYC to start with 
4. Action item and next steps

## Meeting - 2 July 2024 - (1300 ET)

Attendees: Jim Schoening, Alex Hache, Otto Mora, Kim Duffy, Adrian Field, Valerio Massimo Camaiani, Alfonso Gomez Jordana Manas

1. Welcome and introductions
2. Administrivia
3. Review of issues and pull requests
4. ISO MDL review: https://github.com/decentralized-identity/credential-schemas/issues/1
     - [ISO MDL Attributes](https://docs.google.com/spreadsheets/d/1kn9jvb91wd_-xA_3ale3M6Lwn-OM6qem/edit?usp=sharing&ouid=116182654223161791531&rtpof=true&sd=true)
5. Focal use cases: https://github.com/decentralized-identity/credential-schemas/issues/2
6. What's needed:
    - Discussion: grouping of terms into schema to enable consistent meaning and interoperability
    - Grouping, field names, semantics in scope
    - Permanent URLs to groupings: make links available and discoverable
7. Action item and next steps
    - Strawman of abstract data model, get feedback

## Meeting - 18 Jun 2024 - (1300 ET)

Attendees: Jim Schoening, Alex Hache, Gerald Glickman, Alfonso Gomez Jordana Manas, Don Sheppard, Valerio Massimo Camaiani, Eric Scouten, Maria Teresa Aarao, Keith Kowal, Otto Mora, Kim Duffy, Limari Navarrette 

1. Welcome and Procedural Considerations
2. Introductions
3. Review [slides](https://docs.google.com/presentation/d/1QsViPPwtKhFFH6d9kdHiAkSnxJnqK1GV5f_ln3SgNnE/edit#slide=id.p1)
    - Kim reviewed intro material
    - Otto presented donated schema
4. Discussion
    - How did you reconcile aligning with other standards:
        - OpenID and EBSI didn't differ much: casing
        - Feedback from partners
    - How did you handle naming:
        - Provided both to allow full name and piece-by-piece (surname, etc)
    - Interest in discoverability of registries
        - There is a precedent of this in DIF; we're thinking about re-activating, based on member feedback
        - Schemas could live here or elsewhere
    - Suggestion to take mdl schema and align as closely as possible. Input will be coming from passports or driver's license
        - Not an either/or; we'll double-check to help ensure alignment
    - Use cases?
5. Action items and next steps
    - How do we talk about the ISO mdl without paying for it?
    - KYC Use Cases
    - Align with ISO mdl

## Meeting Template

1. Welcome and introductions
2. [WG participation tracking](https://docs.google.com/spreadsheets/d/12hFa574v5PRrKfzIKMgDTjxuU6lvtBhrmLspfKkN4oE/edit#gid=0)
3. Review of issues and pull requests
4. Main topics
5. Action
