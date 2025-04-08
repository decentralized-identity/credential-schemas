# DIF Schemas Repository

This repository, maintained by the Decentralized Identity Foundation (DIF), serves as a centralized hub where organizations and individuals can store, reference, search, and reuse credential schemas. It provides a collaborative platform that enables the community to work towards standardizing widely-adopted credential schema patterns. 

It is organized into three distinct folders to manage schemas at different stages of maturity and standardization:

- `community-schemas/`: Provides a space for individual entities to permanently store and reference their internal schemas. This allows entities to contribute their schemas, serving as a source for identifying patterns and candidates for future standardization.
- `dif-draft-schemas/`: Houses schemas currently under review by the DIF Schemas Working Group, representing potential future standards.
- `dif-recommended-schemas/`: Contains approved, standardized schemas that have completed the DIF review process. These schemas are immutable and serve as permanent references for the community.

# DIF Credential Schemas Work Item

This group meets every other week on Tuesdays at 10am PT / 1pm ET. Calendar link: https://calendar.app.google/MEvzr6ZfXv4HpuND6

## Resources
- [Running agenda and notes](AGENDA.md)
- [Working group recordings](https://docs.google.com/spreadsheets/d/1wgccmMvIImx30qVE9GhRKWWv3vmL2ZyUauuKx3IfRmA/edit?gid=1791063490#gid=1791063490)
- Group kick off call
  - [Recording](https://youtu.be/9aIIuC9xiWI?feature=shared) 
  - [Recap blog](https://blog.identity.foundation/webinar-streamlining-kyc/) 

## [Latest Editor's Draft](https://identity.foundation/credential-schemas/)

## Building the spec

```
git clone git@github.com:decentralized-identity/credential-schemas.git
cd credential-schemas
npm i
npm run edit
npx serve build
```

Visit http://localhost:3000/
