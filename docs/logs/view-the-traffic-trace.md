# View the API Traffic Trace

To debug an API issue using the [Traffic Trace dashboard](/docs/logs/debugging-API-issues.md), follow these steps:

## Complete the prerequisites

Ensure that you have:

- An active [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass) account.
- Access to your Elastic Cloud deployment.
</details>

## Step 1: View the Traffic Trace dashboard

1. Access your StackOps account.

    - **Production:** [go.gov.sg/apex-report](http://go.gov.sg/apex-report)<br>
    - **Staging:** [go.gov.sg/apex-report-stg](http://go.gov.sg/apex-report-stg)

1. Log in with [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your project space.

1. From the main menu, go to the Analytics category and click **Dashboard**. A list of available dashboards are displayed in the Dashboards page.

1. From the list of dashboards, click **Traffic trace**. The Traffic Trace dashboard is displayed.

![dashboard](/./images/dashboard.gif)


## Step 2: Find the Correlation ID

1. On your Traffic Trace dashboard, configure the **Time range**, **App Org**, **App Name**, **Gateway**, and **API Final Status** filters to narrow down the list of API requests in the Traffic Summary panel.

![Select dashboard filters](/./images/dashboard-filters.png) 

| Filter | Description | Used for |
| --- | -- | -- |
| **(1) Time range** | Specifies the time range that the API was processed. | All panels
| **(2) CorrelationID** | Filters or identifies a specific API request in a query. | All panels
| **(3) App Org** | Filters the requests by application's consumer  organisation | Traffic Summary panel
| **(4) App Name** | Filters the requests by application name | Traffic Summary panel
| **(5) Gateway** | Filters the gateway type by either **internal** or **external** values. | Traffic Summary panel
| **(6) API Final Status** | Filters the status of the request by either **Pass** or **Fail** values. | Traffic Summary panel
| **(7) Log level** | Filters the log levels in the Traffic Trace panel. | Traffic trace panel |
    > **Note:** You can choose to skip this step and proceed to browse the list of API requests in the Traffic Summary panel. These requests will be sorted based on the default time range that is set in your dashboard.

1. Browse through the list of API requests in the Traffic Summary panel, and copy the **Correlation ID** of the problematic request.

    ![copy correlation ID](/./images/dashboard-correlationid.png) 

    > **Note:** You can also hover over the Correlation ID entry and  click the (**+**) icon to filter the results by that value.

## Step 3: Debug the problematic request

?> Make sure to clear any filters that you used to find the Correlation ID.

1. In the Correlation ID filter, paste the value of the Correlation ID that corresponds to the problematic API request.

    ![paste correlation ID](/./images/dashboard-correlationid-filter.png) 

1. After filtering by the Correlation ID, debug the request using the **Traffic Details** and **Traffic Trace Root Cause** panels. Proceed to the next sections.

- [View the Traffic Details](/docs/logs/verify-api-request.md)
- [View the Traffic Trace Root Cause](/docs/logs/trace-root-cause.md)



<!-- 

## Step 4: View the Traffic Trace Root Cause

?> Make sure to clear any filters that you used to find the Correlation ID.

1. In the Correlation ID filter, paste the value of the Correlation ID that corresponds to the problematic API request.

    ![paste correlation ID](/./images/dashboard-correlationid-filter.png) 

1. Scroll down to the Traffic Trace panel and check the details in the message column to trace the root cause of the error or issue.

    ![traffic-trace-message](/./images/dashboard-trace-error.png) 

### Export the trace logs

To export the track trace logs in `.csv` format, follow these steps:

1. Hover over the upper right area of the Traffic Trace panel and click the menu icon.

1. Click **More**.

1. Click **Download CSV**.

    ![traffic-trace-message](/./images/dashboard-traffic-trace-export.png) 

-->