# Debugging API issues

To debug a problematic API request, you can trace the request using its **Correlation ID**. 

When an API request is made, a unique Correlation ID is generated and attached to the request message. By tracing the Correlation ID and view the logs related to that ID, you can  pinpoint the source of the error or issue and identify the root cause of the problem.

The **Traffic Trace Dashboard** helps you view and filter the list of the Correlation IDs and the details of each API request. 

<figure style="text-align: center">
  <img
    src="/images/dashboard-traffic-trace.png"/>
	  <figcaption>Fig 1: Traffic Trace Dashboard</figcaption>
</figure>

The dashboard consists of three panels.

| Panel | Description |
| --- | --- |
| **Traffic Summary** | Lists all the Correlation IDs that occurred in a specific time range. The API requests listed by their Correlation ID, which identifies a specific API request or response. |
| **Traffic Details** | Shows the detailed results of the queried API endpoints. The details can determine whether an API call is bridging, such as when the **sentHeader** column returns two Correlation IDs. |
| **Traffic Trace** | Shows the trace level for the  queried API. The details provided in this panel are used to debug the API request.


To debug an API issue using the Traffic Trace dashboard, follow these steps:

- [Fulfill the prerequisites](#prerequisites)
- [Step 1: View the traffic trace dashboard](#step-1-view-the-traffic-trace-dashboard)
- [Step 2: Use the traffic trace dashboard](#step-2-use-the-traffic-trace-dashboard)

## Prerequisites
You need:
- an active [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass) account.
- access to your Elastic Cloud deployment.


## Step 1: View the Traffic Trace dashboard

1. Access your Elastic Cloud deployment: https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/.

1. Log in with [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your project space.

1. From the main menu, go to the Analytics category and click **Dashboard**. A list of available dashboards are displayed in the Dashboards page.
 
    ![Select dashboard menu](/images/dashboard-menu.png) 

1. From the list of dashboards, click **Traffic trace**. The Traffic Trace dashboard is displayed.


## Step 2: Use the Traffic Trace dashboard

To debug a specific API request, you can use the available filters in the dashboard to narrow down the data displayed in the panels.

| Filter | Description | Used for |
| --- | -- | -- |
| **Time range** | Specifies the time range that the API was processed. | All panels
| **CorrelationID** | Filters or identifies a specific API request in a query. | All panels
| **Gateway** | Filters the gateway type by either **internal** or **external** values. | Traffic Summary panel
| **API Final Status** | Filters the status of the request by either **Pass** or **Fail** values. | Traffic Summary panel
| **Log level** | Filters by the log levels in the Traffic Trace panel. | Traffic trace panel |

1. On your Traffic Trace dashboard, use the **Time range**, **Gateway**, and **API Final Status** filters to narrow down the list of API requests in the Traffic Summary panel.

1. Browse through the list of API requests in the Traffic Summary panel, and copy the **Correlation ID** of the problematic request.
    > Note: You can also hover over the Correlation ID entry and  click the (+) icon to filter the results by that value.

1. In the Correlation ID filter, paste the value of the Correlation ID that you copied in the previous step, which corresponds to the problematic API request.

1. View the Traffic Trace panel and check the details in the message column to trace the root cause of the error or issue.


<!-- >
1. Configure the following filters as needed.

a. **Time range** - Specifies the time range that the API was processed.<br>
b. **CorrelationID** - Filters or identifies a specific API request in a query. <br>
c. **Gateway** - Filters the gateway type by either **internal** or **external** values.<br>
d. **API Final Status**- Filters the status of the request by either **Pass** or **Fail** values.<br>
e. **Log level** - Filters by the log levels in the Traffic Trace panel. <br>

    **Notes:**
    - If you already selected a specific request using the  Correlation ID filter, clear the rest of the filters.
    - If you are not getting any data in the dashboard panels, check the filter values.

1. 
---


## Step 1: Identify the correlation ID of the problematic API request

1. Go to the APEX Cloud Elastic Cloud deployment: <br>
    https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/. 

1. Log in with [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your project space.

    ![Select your space](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/login-spaces.png ":size=230") 

1. From the menu on the upper left of the dashboard, navigate to the Analytics category and click **Discover**. 

    ![Discover](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/discover.png ":size=150")

1. In Discover, open the data view dropdown and select  the **apigw-traffic-summary** data view. 

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

    ![View the stack trace](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace.png)

1. On the KQL search field, enter a query for the correlation ID parameter obtained in the previous steps.

    For example, `correlationId : ac25ff63feabb71075ce47f5`

1. Submit the query. A list of stack traces that correspond to the correlation ID are displayed in the document table.

## Step 3: Review the strack trace logs 

1. From the list of Available fields, add the **timestamp**, **correlationId**, and **message** fields to the document table to simplify your view: 

    ![Stack trace fields](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace-fields.png ":size=220")

1. Browse through the list and review the logs in the **message** column to see the sequence of method calls and diagnose any issues. Analyze the stack trace to identify the specific line of code that caused the error or exception.

    ![Stack trace messages](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace-messages.png)

### Next steps

To further narrow down your search, you can also filter the stack trace logs based on the issue encountered. Proceed to [Filtering common issues](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/filtering-common-issues).

<!-- 
# Debugging API issues

You can check the stack trace of a problematic API request to see any errors or exceptions that occurred. 

## Prerequisites
You need:
- An active [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass) account
- Access to your Elastic Cloud deployment

To view stack trace logs, follow these steps:

- [Step 1: Identify the correlation ID of the problematic API request](#step-1-identify-the-correlation-id-of-the-problematic-api-request)
- [Step 2: Display the stack traces that correspond to the correlation ID](#step-2-display-the-stack-traces-that-correspond-to-the-correlation-id)
- [Step 3: Review the strack trace logs](#step-3-review-the-strack-trace-logs)

## Step 1: Identify the correlation ID of the problematic API request

1. Go to the APEX Cloud Elastic Cloud deployment: <br>
    https://gvt-gds-apex-apex-stg.kb.ap-southeast-1.aws.found.io/. 

1. Log in with [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your project space.

    ![Select your space](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/login-spaces.png ":size=230") 

1. From the menu on the upper left of the dashboard, navigate to the Analytics category and click **Discover**. 

    ![Discover](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/discover.png ":size=150")

1. In Discover, open the data view dropdown and select  the **apigw-traffic-summary** data view. 

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

    ![View the stack trace](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace.png)

1. On the KQL search field, enter a query for the correlation ID parameter obtained in the previous steps.

    For example, `correlationId : ac25ff63feabb71075ce47f5`

1. Submit the query. A list of stack traces that correspond to the correlation ID are displayed in the document table.

## Step 3: Review the strack trace logs 

1. From the list of Available fields, add the **timestamp**, **correlationId**, and **message** fields to the document table to simplify your view: 

    ![Stack trace fields](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace-fields.png ":size=220")

1. Browse through the list and review the logs in the **message** column to see the sequence of method calls and diagnose any issues. Analyze the stack trace to identify the specific line of code that caused the error or exception.

    ![Stack trace messages](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/stack-trace-messages.png)

### Next steps

To further narrow down your search, you can also filter the stack trace logs based on the issue encountered. Proceed to [Filtering common issues](https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/docs/logs/filtering-common-issues).

-->