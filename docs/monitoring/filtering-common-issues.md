# Filtering common issues

To filter the stack trace logs by the most common issues, use the specified syntax below.

## Prerequisite

Find the correlation ID and view the stack traces related to the problematic API request. Refer to [Viewing stack trace](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/monitoring/viewing-stack-trace).

## Filter that caused failure

On the KQL search field, enter this query:

`Correlation ID + message : "Filter that caused failure"`

##  Unable to find Key ID in JWKS

On the KQL search field, enter this query:

`Correlation ID + message: "Unable to find Key Id in JWKS"`

