# Verify the API request to the endpoint

To verify the client or application that has made a request to the APEX Cloud API endpoint, you can check the **X-Forwarded-For** header. 

1. Find the the Correlation ID of the specific API request and filter the traffic trace logs by that correlation ID. You can refer to the steps in [View the API Traffic Trace](#view-the-api-traffic-trace).
2. Locate the header in the **transactionElements.leg0.protocolInfo.recvHeader** column in the Traffic Details panel.


![traffic-trace-message](/images/dashboard-traffic-details-header.png) 

**Syntax**<br>
`X-Forwarded-For: <client>, <proxy1>, <proxy2>`

The `<client>` value refers to the source IP address of the application that initiated the API request to the APEX Cloud endpoint.