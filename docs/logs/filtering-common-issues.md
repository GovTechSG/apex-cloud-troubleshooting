# Filtering common issues

To filter the stack trace logs by the most common issues, use the query below.

## Prerequisite

You need to complete the steps in [Viewing stack trace](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/viewing-stack-trace).

## Query syntax

On the KQL search field, enter a combined query for the following parameters:

- `correlationId` 
- `message`

For example:<br>
`correlationId : "2127f7633adaffa5bae26858" AND message : "Filter that caused failure"`

See the list of issues below to filter your stack trace logs using the `message` parameter.

- `Filter that caused failure` 
- `Unable to find Key ID in JWKS`

<!--
The table below lists the issues that you can use for your query to filter your stack trace logs.

| Common issues|   
| -- |  
| Filter that caused failure | 
| Unable to find Key ID in JWKS | 



## Filter that caused failure

On the KQL search field, enter this query:

`Correlation ID + message : "Filter that caused failure"`

##  Unable to find Key ID in JWKS

On the KQL search field, enter a combined query for the following fields:

correlationId : "2127f7633adaffa5bae26858" AND message : "Unable to find Key ID in JWKS"

`Correlation ID + message: "Unable to find Key Id in JWKS"`

-->