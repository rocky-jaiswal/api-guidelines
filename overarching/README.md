# Overarching guidelines

## Follow API First Principle

- You must define APIs first, before coding its implementation

## Provide API Specification using OpenAPI

- We use the [Open API specification](https://swagger.io/specification/) as standard to define API specifications files. API designers have to provide the API specification files using YAML to improve readability. We encourage to use OpenAPI 3.0 version, but still support OpenAPI 2.0 (a.k.a. Swagger 2).

- The API specification files should be subject to version control using a source code management system - best together with the implementing sources.

## Write APIs & documentation in U.S. English

## Versioning

APIs must be subject to version control. The version number of an API appears in its URI. For example, use this URI structure to request version 1 of the ‘upm’ API:

- http://host:port/context/rest/upm/1/...

## Contain API Meta Information

APIs must contain endpoints for -

- Version information
- Description
- Contact person/s
- Health checks

## Use Semantic Versioning

Follow semantic versioning rules for all APIs

- Increment the MAJOR version when you make incompatible API changes after having aligned this changes with consumers,
- Increment the MINOR version when you add new functionality in a backwards-compatible manner, and
- Optionally increment the PATCH version when you make backwards-compatible bug fixes or editorial changes not affecting the functionality.

## When to Change the Version

A version number indicates a certain level of backwards-compatibility the client can expect, and as such, extra care should be taken to maintain this trust. The following lists which types of changes necessitate a new version and which don’t:

Changes That Don’t Require a New Version
- New resources
- New HTTP methods on existing resources
- New data formats
- New attributes or elements on existing data types

Change That Require a New Version
- Removed or renamed URIs
- Different data returned for same URI
- Removal of support for HTTP methods on existing URIs
