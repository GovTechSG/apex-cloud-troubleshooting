# General Troubleshooting

APEX Cloud provides categorized data views on the Elastic Cloud platform. These data views can help users review specific types of data logs and messages. To narrow down the data further, additonal filters can be applied to these views.

To troubleshoot errors from log messages, follow these steps:
<!--


How about logging in?
Navigating to "space"?

Questions:
- are we sharing the staging link to Elastic platform? or is there a prod link?
- what if user is not a public officer (corppass account)? how do they log in?
- agency users - do they see all the spaces or do they go to a default space?
- 

-->

1. Go to the APEX Cloud Elastic Cloud Platform: https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/. *[Note: prod link?]*

1. Click **Log in with TechPass**. *[For corppass?]*

1. Select your TechPass account.

    [- Select your space?]

   The Elastic Cloud dashboard is displayed.

1. Click the hamburger icon on the upper left of the dashboard to open the menu. The sidebar menu is displayed.

1. Under the Analytics category, click **Discover**.

1. From the list of data views, select the **apigw-traffic-summary** data view.

1. From the time range options, choose a time range or select any of the commonly used time ranges.

1. On the KQL search field, enter the following filter:
`http.uri = {API path} and processinfo.gatewayName : {'Internal' or 'External'}`

    Replace the values inside the brackets with the appropriate values. For example: `http.uri: \nyp-ioc-ip and processinfo.gatewayName  : External `
    - API path - The API base path
    - External - internet zone

--

1. Find correlation ID

    Discover -> apigw-traffic-summary data view (data view term is new term)ß
    Set the date range

    Use this filter: `http.uri: \nyp-ioc-ip and processinfo.gatewayName  : External `

    http.uri = API path
    External = internet
    Internal = intranet

    Find the `correlationID`

2. View stack trace

    Discover -> apigw-traffic-trace data view 

    Add the columns:

        - correlationId
        - messsage
    And that's the entire stack trace


If you want to go further:

    1a. Can go to common issues
    1b. Can go to 

