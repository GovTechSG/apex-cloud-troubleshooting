# Viewing trace logs

To troubleshoot and resolve API issues, you can review stack trace logs in the Elastic Cloud deployment. To view the logs, you need to identify the correlation ID of the specific request that led to the error, and then use that correlation ID to view the stack trace of that request. The stack trace provides detailed information about the sequence of method calls that led to the error.

### Prerequisites
You need to have:
- An active TechPass account [?]
- Access to your Elastic Cloud deployment [?]

To view stack trace logs, follow these steps:
<!--
logging in?
Navigating to "space"?

Questions:
- are we sharing the staging link to Elastic platform? or is there a prod link?
- what if user is not a public officer (corppass account)? how do they log in?
- agency users - do they see all the spaces or do they go to a default space?
-->

- [STEP 1: Identify the correlation ID of the problematic API request](#step-1-identify-the-correlation-id-of-the-problematic-api-request)
- [Step 2: Generate the list of stack traces related to the correlation ID](#step-2-generate-the-list-of-stack-traces-related-to-the-correlation-id)
- [STEP 3: Browse the stack trace list and review the logs](#step-3-browse-the-stack-trace-list-and-review-the-logs)

### Step 1: Identify the correlation ID of the problematic API request

1. Go to the APEX Cloud Elastic Cloud Platform: https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/. *[Note: prod link?]*

1. Click **Log in with TechPass**. *[For corppass?]*

1. Select your TechPass account.

    [- Select your space?]

   The Elastic Cloud dashboard is displayed.

1. Click the hamburger icon on the upper left of the dashboard to open the menu. The sidebar menu is displayed.

1. Under the Analytics category, click **Discover**.

1. In Discover, open the data view dropdown, and select the **apigw-traffic-summary** data view.

1. Click the time range icon, and select a time range.

1. On the KQL search field, enter a query with the following fields:
    - http.uri - refers to the API base path
    - processinfo.gatewayName - can be external (internet) or internal (intranet)

    For example: `http.uri: \nyp-ioc-ip and processinfo.gatewayName  : External`

1. Submit the query. (Press enter?) A list of documents that match the query are displayed in the document table.

1. Browse through the documents list and identify the problematic API request.

1. Copy the `correlationId` value of the problematic API request.

### Step 2: Generate the list of stack traces related to the correlation ID

1. Open the data view dropdown, and select the **apigw-traffic-trace** data view.

1. On the KQL search field, enter a query for the `correlationId` field. 

    For example, `correlationId :ac25ff63feabb71075ce47f5`

1. Submit the query. A list of documents that match the query are displayed in the document table.

### Step 3: Review the strack trace logs 

1. From the list of **Available fields**, add the following fields as columns in the document table to simplify the view:
    - `timestamp`
    - `correlationId`
    - `message`

1. Browse through the list and review the logs in the **message** column to see the sequence of method calls and diagnose any issues.

### Next steps

To further narrow down the stack trace logs list, you can filter the messages by the specific errors. Proceed to <link>.

<!--

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

-->