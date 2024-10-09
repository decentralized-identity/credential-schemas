# Credential Schemas Repository

Welcome to the Credential Schemas repository. This shared repository acts as a common storage location for credential schemas, enabling standardized and easy access to schemas across different contributors. 

## Structure and Purpose

This repository is structured to facilitate easy organization and retrieval of credential schemas by following these guidelines:

- **Shared Repo:** The repository serves as a shared location where credential schemas are stored for common use. 
- **Submitter Folders:** Schemas are organized in submitter folders. Each submitter will have their own folder, making it easy to locate schemas based on the entity that provided them.

## Custom Submissions and DIF Standardization

Please note that the schemas submitted to this repository are **custom submissions** by individual entities and do not represent **DIF standard schemas**. 

The **Decentralized Identity Foundation (DIF)** will closely monitor the submissions made to this repository, with the intention of identifying schemas that may become standardized in the future. The goal is to standardize specific schemas according to their comprehensive design and broad adoption in the ecosystem. While this standardization process may take time, it ensures alignment with best practices and long-term interoperability.

## Submission Process and Rules

Please follow these rules when submitting schemas to this repository:

1. **First-Time Submitter Review:**
   - If you are submitting a schema for the first time, you will need to create a new folder with your entity's name or unique identifier. 
   - Your folder submission will require a manual review by a DIF admin. DIF repo admins are found in the root [CODEOWNERS](./CODEOWNERS) file. This is to ensure that the submission complies with repository guidelines, content policies and standards. 
   - Automated content moderation processes are planned for future implementation, but for now, all first-time submitter folders are manually reviewed.

2. **Submitter Folder Requirements:**
   - Each submitter folder must include a `README.md` file explaining who the submitter is and providing relevant information about the schemas inside.
   - Each submitter folder must include a `CODEOWNERS` file listing the schema contributors and reviewers for that folder.
   
3. **Schema Submission & Compliance:**
   - All schemas provided in this repository should comply with recognized standards. Primarily, schemas must adhere to the [W3C Verifiable Credential](https://www.w3.org/TR/vc-data-model/) standard or other schema definitions based on standards like [EIP-721](https://eips.ethereum.org/EIPS/eip-721) or [VC-JWT](https://www.w3.org/TR/vc-jose-cose/). 
   - The following [VC JSON Schema format](https://www.w3.org/TR/vc-json-schema/#example-example-name-credential-schema) is a good example to follow.

By adhering to these rules, we ensure the quality, organization, and interoperability of schemas across the ecosystem. 