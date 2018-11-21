# Overarching guidelines

## Follow API First Principle

- You must define APIs first, before coding its implementation

## Provide API Specification using OpenAPI

- We use the [Open API specification](https://swagger.io/specification/) as standard to define API specifications files. API designers have to provide the API specification files using YAML to improve readability. We encourage to use OpenAPI 3.0 version, but still support OpenAPI 2.0 (a.k.a. Swagger 2).

- The API specification files should be subject to version control using a source code management system - best together with the implementing sources.

## Provide API documentation

- Write documentation in simple makrdown format on Gitlab

## Write APIs & documentation in U.S. English

## Versioning

APIs must be subject to version control. The version number of an API appears in its URI. For example:

- http://host:port/api/v1/...

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

## Don’t Break Backward Compatibility

Change APIs, but keep all consumers running. Consumers usually have independent release lifecycles, focus on stability, and avoid changes that do not provide additional value. APIs are contracts between service providers and service consumers that cannot be broken via unilateral decisions.

There are two techniques to change APIs without breaking them:
- follow rules for compatible extensions
- introduce new API versions and still support older versions

## If a new version of an API is released the old version must be kept alive for some time

- Discuss with clients the time needed to keep old version alive
- Do not let new clients use old version
- Monitor usage of old version and retire it when no longer in use


## No verbs in resources only nouns (keep URLs verb free)

REST is all about your resources, so consider the domain entities that take part in web service interaction, and aim to model your API around these using the standard HTTP methods as operation indicators. For instance, if an application has to lock articles explicitly so that only one user may edit them, create an article lock with PUT or POST instead of using a lock action.

Request:

- PUT /article-locks/{article-id}

The added benefit is that you already have a service for browsing and filtering article locks.

## No more than 2 sub-resource type

- e.g. http://api/customers/{id}/addresses/{addr}

## Use consistent naming scheme for APIs

- e.g. <service-name>.<team-name>.<domainname>.com

## Prefer Hyphenated-Pascal-Case for HTTP header Fields

## All APIs should be stateless and seamlessly horizontally scalable

## APIs should allow CORS for development environment, it should be blocked for rest of the environments


