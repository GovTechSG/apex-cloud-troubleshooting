# Viewing stack trace

You can check the stack trace of a problematic API request to see any errors or exceptions that occurred. 

## Prerequisites
You need:
- An active TechPass account
- Access to your Elastic Cloud deployment

To view stack trace logs, follow these steps:

- [Step 1: Identify the correlation ID of the problematic API request](#step-1-identify-the-correlation-id-of-the-problematic-api-request)
- [Step 2: Display the stack traces that correspond to the correlation ID](#step-2-display-the-stack-traces-that-correspond-to-the-correlation-id)
- [Step 3: Review the strack trace logs](#step-3-review-the-strack-trace-logs)

## Step 1: Identify the correlation ID of the problematic API request

1. Go to the APEX Cloud Elastic Cloud Platform: <br>
    https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/. 

1. [Log in with TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your agency space.

    ![Select your space](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/login-spaces.png ":size=230") 

1. Click the hamburger icon menu on the upper left of the dashboard. The sidebar menu is displayed. 

1. Under the Analytics category, click **Discover**. 

    ![Discover](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/discover.png)

1. In Discover, open the data view dropdown, and select the **apigw-traffic-summary** data view. The traffic summary is displayed.

    ![Find the correlation ID](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/find-correlation-ID.png)

1. Click the time range icon, and select a time range. 

1. On the KQL search field, enter a combined query for the following parameters:
    - **http.uri** - Refers to the API base path.
    - **processinfo.gatewayName** - Can be external (internet) or internal (intranet).

    For example: `http.uri: \nyp-ioc-ip and processinfo.gatewayName  : External`

1. Submit the query. A list of logs that match the query are displayed in the document table. 


1. Browse through the logs and identify the problematic API request.

1. Copy the **correlationId** value of the problematic API request.

## Step 2: Display the stack traces that correspond to the correlation ID

1. Open the data view dropdown, and select the **apigw-traffic-trace** data view.

1. On the KQL search field, enter a query for the correlation ID parameter obtained in the previous steps.

    For example, `correlationId : ac25ff63feabb71075ce47f5`

1. Submit the query. A list of stack traces that correspond to the correlation ID are displayed in the document table.

## Step 3: Review the strack trace logs 

1. From the list of **Available fields**, add the following fields as columns in the document table to simplify your view:
    - **timestamp**
    - **correlationId**
    - **message**

1. Browse through the list and review the logs in the **message** column to see the sequence of method calls and diagnose any issues. Analyze the stack trace to identify the specific line of code that caused the error or exception

### Next steps

To further narrow down your search, you can also filter the stack trace logs based on the issue encountered. Proceed to [Filtering common issues](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/filtering-common-issues).