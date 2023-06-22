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
 
    ![Select dashboard menu](/images/dashboard-menu.png) 

1. From the list of dashboards, click **Traffic trace**. The Traffic Trace dashboard is displayed.

You can use the available filters in the dashboard to narrow down the data displayed in the panels.

![Select dashboard filters](/./images/dashboard-filters.png) 

| Filter | Description | Used for |
| --- | -- | -- |
| **(1) Time range** | Specifies the time range that the API was processed. | All panels
| **(2) CorrelationID** | Filters or identifies a specific API request in a query. | All panels
| **(3) Gateway** | Filters the gateway type by either **internal** or **external** values. | Traffic Summary panel
| **(4) API Final Status** | Filters the status of the request by either **Pass** or **Fail** values. | Traffic Summary panel
| **(5) Log level** | Filters by the log levels in the Traffic Trace panel. | Traffic trace panel |


## Step 2: Find the Correlation ID

1. On your Traffic Trace dashboard, configure the **Time range**, **Gateway**, and **API Final Status** filters to narrow down the list of API requests in the Traffic Summary panel.
    > **Note:** You can choose to skip this step and proceed to browse the list of API requests in the Traffic Summary panel. These requests will be sorted based on the default time range that is set in your dashboard.

1. Browse through the list of API requests in the Traffic Summary panel, and copy the **Correlation ID** of the problematic request.

    ![copy correlation ID](/./images/dashboard-correlationid.png) 

    > **Note:** You can also hover over the Correlation ID entry and  click the (**+**) icon to filter the results by that value.

## Step 3: View the traffic trace

1. Clear any filters that you used to find the Correlation ID.

1. In the Correlation ID filter, paste the value of the Correlation ID that corresponds to the problematic API request.

    ![paste correlation ID](/./images/dashboard-traffic-details-header.png) 

1. Scroll down to the Traffic Trace panel and check the details in the message column to trace the root cause of the error or issue.

    ![traffic-trace-message](/./images/dashboard-trace-error.png) 

### Export the track trace logs

To export the track trace logs in `.csv` format, follow these steps:

1. Hover over the upper right area of the Traffic Trace panel and click the menu icon.

1. Click **More**  > **Download CSV**.

    ![traffic-trace-message](/./images/dashboard-traffic-trace-export.png) 
