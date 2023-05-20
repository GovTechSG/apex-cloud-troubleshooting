# Debugging API request issues

To debug a problematic API request, you can trace the request using its **Correlation ID**. 

When an API request is made, a unique Correlation ID is generated and attached to the request message. By tracing the Correlation ID and view the logs related to that ID, you can  pinpoint the source of the error or issue and identify the root cause of the problem.

The Traffic Trace Dashboard helps you view and filter the list of the Correlation IDs and the details of each API request. 

<figure style="text-align: center">
  <img
    src="https://docs.developer.tech.gov.sg/docs/apex-cloud-troubleshooting-guide/images/dashboard-traffic-trace.png"/>
	  <figcaption>Fig 1: Traffic Trace Dashboard</figcaption>
</figure>

The dashboard consists of three panels.

| Panel | Description |
| --- | --- |
| **Traffic Summary** | Lists all the Correlation IDs that occurred in a specific time range. The API requests listed by their Correlation ID, which identifies a specific API request or response. |
| **Traffic Details** | Shows the detailed results of the queried API endpoints. The details can determine whether an API call is bridging, such as when the **sentHeader** column returns two Correlation IDs. |
| **Traffic Trace** | Shows the trace level for the  queried API. The details provided in this panel are used to debug the API request.

## View the API Traffic Trace

To debug an API issue using the Traffic Trace dashboard, follow these steps:

#### Prerequisites
- An active [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass) account.
- Access to your Elastic Cloud deployment.

<details><b><summary style="font-size:20px">Step 1: View the Traffic Trace dashboard</b></summary>

1. Access your StackOps account.

    - **Production:** [go.gov.sg/apex-report](http://go.gov.sg/apex-report)<br>
    - **Staging:** [go.gov.sg/apex-report-stg](http://go.gov.sg/apex-report-stg)


1. Log in with [TechPass](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/docs/techpass). The Elastic Cloud dashboard is displayed. 

1. From the Spaces menu, select your project space.

1. From the main menu, go to the Analytics category and click **Dashboard**. A list of available dashboards are displayed in the Dashboards page.
 
    ![Select dashboard menu](/images/dashboard-menu.png) 

1. From the list of dashboards, click **Traffic trace**. The Traffic Trace dashboard is displayed.

You can use the available filters in the dashboard to narrow down the data displayed in the panels.

![Select dashboard filters](/images/dashboard-filters.png) 

| Filter | Description | Used for |
| --- | -- | -- |
| **(1) Time range** | Specifies the time range that the API was processed. | All panels
| **(2) CorrelationID** | Filters or identifies a specific API request in a query. | All panels
| **(3) Gateway** | Filters the gateway type by either **internal** or **external** values. | Traffic Summary panel
| **(4) API Final Status** | Filters the status of the request by either **Pass** or **Fail** values. | Traffic Summary panel
| **(5) Log level** | Filters by the log levels in the Traffic Trace panel. | Traffic trace panel |
</details>

<details><b><summary style="font-size:20px">Step 2: Find the Correlation ID</b></summary>

1. On your Traffic Trace dashboard, configure the **Time range**, **Gateway**, and **API Final Status** filters to narrow down the list of API requests in the Traffic Summary panel.
    > **Note:** You can choose to skip this step and proceed to browse the list of API requests in the Traffic Summary panel. These requests will be sorted based on the default time range that is set in your dashboard.

1. Browse through the list of API requests in the Traffic Summary panel, and copy the **Correlation ID** of the problematic request.

    ![copy correlation ID](/images/dashboard-correlationid.png) 

    > **Note:** You can also hover over the Correlation ID entry and  click the (**+**) icon to filter the results by that value.
</details>

<details><b><summary style="font-size:20px">Step 3: View the traffic trace</b></summary>

1. Clear any filters that you used to find the Correlation ID.

1. In the Correlation ID filter, paste the value of the Correlation ID that corresponds to the problematic API request.
    ![paste correlation ID](/images/dashboard-traffice-details-header.png) 

1. Scroll down to the Traffic Trace panel and check the details in the message column to trace the root cause of the error or issue.
    ![traffic-trace-message](/images/dashboard-trace-error.png) 

**Export the track trace logs in .csv format**

1. Hover over the upper right area of the Traffic Trace panel and click the menu icon.

1. Click **More**.

1. Click **Download as CSV**.

    ![traffic-trace-message](/images/dashboard-traffic-trace-export.png) 

</details>

## Verify the API request to the endpoint

To verify that a client or application has made a request to the APEX Cloud API endpoint, you can check the **X-Forwarded-For** header. 

![traffic-trace-message](/images/dashboard-traffic-details-header.png) 

Locate the header in the **transactionElements.leg0.protocolInfo.recvHeader** column in the Traffic Details panel.

**Syntax**<br>
`X-Forwarded-For: <client>, <proxy1>, <proxy2>`

The `<client>` value refers to the source IP address of the application that initiated the API request to the APEX Cloud endpoint.




