# Data

## Data transfer must be in JSON

## Property names must be ASCII snake_case (and never camelCase): ^[a-z_][a-z_0-9]*$

## Boolean property values must not be null

## Empty array values should not be null

- Empty array values can unambiguously be represented as the empty list, [].

## Enumerations should be represented as Strings

## Time durations and intervals should conform to ISO 8601

## Do not expose Stack Traces

- Stack traces contain implementation details that are not part of an API, and on which clients should never rely. Moreover, stack traces can leak sensitive information that partners and third parties are not allowed to receive and may disclose insights about vulnerabilities to attackers.
- Error messages should also not include SQL queries or any information about the underlying systems (servers / DB in use etc.)

## Always support pagination of data

## Use snake_case (never camelCase) for Query Parameters

## Use ISO_3166-1_alpha-2 for country codes
