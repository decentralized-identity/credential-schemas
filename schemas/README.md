# Credential Schemas Repository

Welcome to the Credential Schemas repository. This shared repository acts as a common storage location for credential schemas, enabling standardized and easy access to schemas across different categories and contributors. 

## Structure and Purpose

This repository is structured to facilitate easy organization and retrieval of credential schemas by following these guidelines:

- **Shared Repo:** The repository serves as a shared location where credential schemas are stored for common use. 
- **Category Folders:** Schemas are organized into category folders, which are defined by the administrators of the repository. This repository is managed by the Decentralized Identity Foundation (DIF) admins. Categories are meant to represent the purpose or domain of the schemas they contain.
- **Submitter Folders:** Inside each category folder, schemas are further organized by submitter. Each submitter will have their own folder, making it easy to locate schemas based on the entity that provided them.

This structure ensures that schemas can be easily categorized and accessed based on their intended use and origin.

## Proprietary Submissions and W3C Standardization

Please note that the schemas submitted to this repository are **proprietary submissions** by individual entities and do not represent **W3C standard schemas**. 

The **World Wide Web Consortium (W3C)** will closely monitor the submissions made to this repository, with the intention of identifying schemas that may become standardized in the future. The goal is to standardize specific schemas according to their comprehensive design and broad adoption in the ecosystem. While this standardization process may take time, it ensures alignment with best practices and long-term interoperability.

## Initial Categories and Folder Names

Below are the initial categories created to organize schemas in this repository. Submitters should place their schema examples in the appropriate category folder. If a category does not exist for your submission, please refer to the **Submission Process and Rules** section for instructions on creating new categories.

- **Education:** `education/`
  - For schemas related to academic credentials, certifications, and course completions.
  
- **Healthcare:** `healthcare/`
  - For schemas related to medical records, vaccination certificates, and other health-related credentials.

- **Employment & Professional:** `employment-professional/`
  - For schemas related to employment verification, work history, and professional certifications.

- **Finance:** `finance/`
  - For schemas related to financial credentials such as KYC, credit scores, and bank account verification.

- **Government & Legal:** `government-legal/`
  - For schemas related to government-issued IDs, legal documents, and national credentials.

- **Retail & E-Commerce:** `retail-ecommerce/`
  - For schemas related to loyalty programs, purchase receipts, and other e-commerce documents.

- **Travel & Hospitality:** `travel-hospitality/`
  - For schemas related to travel documents, event tickets, and hospitality services.

- **Real Estate:** `real-estate/`
  - For schemas related to property ownership, rental agreements, and real estate transactions.

- **Supply Chain & Logistics:** `supply-chain-logistics/`
  - For schemas related to product certifications, shipping documentation, and supplier credentials.

- **Identity Verification:** `identity-verification/`
  - For schemas related to digital identity verification, including proof of age and residency.

These categories will serve as the starting point for organizing schemas and facilitating easy submission and access.

## Submission Process and Rules

Please follow these rules when submitting schemas to this repository:

1. **Category Folder Definition:**
   - The creation of new category folders is overseen by the Decentralized Identity Foundation (DIF) admins. If you wish to propose a new category, it must be approved by a DIF admin. You can view the current administrators in the [CODEOWNERS](./CODEOWNERS) file.

2. **First-Time Submitter Review:**
   - If you are submitting a folder under a category for the first time, your submission will require a manual review by a DIF admin. This is to ensure that the submission complies with repository guidelines, content policies and standards. 
   - Automated content moderation processes are planned for future implementation, but for now, all first-time submitter folders are manually reviewed.

3. **Submitter Folder Requirements:**
   - Each submitter folder must include a `README.md` file explaining who the submitter is and providing relevant information about the schemas inside.
   - Each submitter folder must include a CODEOWNERS file listing the schema contributors and reviewers for that folder.
   
4. **Schema Submission &Compliance:**
   - All schemas provided in this repository should comply with recognized standards. Primarily, schemas must adhere to the [W3C Verifiable Credential schema definition](https://www.w3.org/TR/vc-data-model/) or other schema definitions based on standards like [EIP-721](https://eips.ethereum.org/EIPS/eip-721) or [VC-JWT](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-vc-jwt-10). 
   - The following [VC JSON Schema format](https://www.w3.org/TR/vc-json-schema/#example-example-name-credential-schema) is a good example to follow when submitting schemas.

By adhering to these rules, we ensure the quality, organization, and interoperability of schemas across the ecosystem. 