# View the Traffic Details

To debug the issue by checking the Traffic Details, follow these steps:

1. In the Correlation ID filter, paste the value of the Correlation ID that corresponds to the problematic API request. Make sure to clear any filters that you previously used to find the Correlation ID.

1. Scroll down to the **Traffic Details - Client to APEX Cloud** and **Traffic Details - APEX Cloud to Endpoint** panels. From here, you can trace the traffic details of the request.


## Client to APEX Cloud panel

Use this panel to determine whether an API request is experiencing failure on the Client to APEX Cloud segment of the request (Leg 0).<br><br>
    ![client-to-apex](/images/trafficdetails-clienttoapex.png) 

- The **X-Forwarded-For** (**1**) header verifies the Client IP address.

    **Syntax**<br>
    `X-Forwarded-For: <TENANT-PUBLIC-IP>, <proxy1>, <proxy2>`

    The <TENANT-PUBLIC-IP> value refers to the Source IP address of the application that initiated the API request.

- The **HTTP response** (**2**) shows the HTTP response. In the example below, the response shows a `446 Client Error`.

    ![client-to-apex](/images/trafficdetails-clienttoapex-error.png) 

- The **X-CorrelationID** (**3**) header determines that the API is a **Bridging API** if there are two correlation ID values. Bridging APIs can be:
    - Backend-hosted in Intranet and exposed in Internet
    - Backend-hosted in Internet and exposed in Intranet

## APEX Cloud to Endpoint panel

Use this panel to determine whether an API request is experiencing failure on the APEX Cloud to Endpoint segment of the request (Leg 1).<br><br>
![apex-to-endpoint](/images/trafficdetails-apextoendpoint.png) 


<!--
# Verify the API request to the endpoint

To verify the client or application that has made a request to the APEX Cloud API endpoint, you can check the **X-Forwarded-For** header. 

1. Filter the traffic trace logs by the correlation ID. You can refer to the steps in [View the API Traffic Trace](/docs/logs/view-the-traffic-trace.md).


2. Locate the header in the **transactionElements.leg0.protocolInfo.recvHeader** column in the Traffic Details panel.


![traffic-trace-message](/images/dashboard-traffic-details-header.png) 

**Syntax**<br>
`X-Forwarded-For: <client>, <proxy1>, <proxy2>`

The `<client>` value refers to the source IP address of the application that initiated the API request to the APEX Cloud endpoint.

-->