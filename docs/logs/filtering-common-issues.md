<!-- 

# Filtering common issues

To filter the stack trace logs by the most common issues, use the query below.

## Prerequisite

You need to [display the stack traces related to the issue](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/viewing-stack-trace) in your Elastic Cloud deployment dashboard.

## Query syntax

On the KQL search field, enter a combined query for the  **correlationId** and **message** parameters.

For example:<br>
`correlationId : "2127f7633adaffa5bae26858" AND message : "Filter that caused failure"`

![Common issues](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/common-issues.png)

### List of common issues

Use any of the common issues below as values for the **message** parameter.

- Filter that caused failure
- Unable to find Key ID in JWKS

-->