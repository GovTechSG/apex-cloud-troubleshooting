# Filtering common issues

To filter the stack trace logs by the most common issues, use the query below.

## Prerequisite

You need to complete the steps in [Viewing stack trace](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/viewing-stack-trace).

## Query syntax

On the KQL search field, enter a combined query for the following parameters:

- **correlationId**
- **message**

For example:<br>
`correlationId : "2127f7633adaffa5bae26858" AND message : "Filter that caused failure"`

### Common issues

Use any of the common issues below as values for the **message** parameter .

- Filter that caused failure
- Unable to find Key ID in JWKS
