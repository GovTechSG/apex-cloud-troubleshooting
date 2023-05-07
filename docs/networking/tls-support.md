# SSL/TLS issues

To troubleshoot SSL/TLS errors, ensure that your system supports the TLS protocol and cipher suites that are supported by APEX Cloud.

1. To retrieve a list of available cipher suites on your system, run the following **PowerShell** command: `Get-TlsCipherSuite | ft Name`

2. Next, you can refer to the table below to see which TLS protocol and cipher suites APEX Cloud supports. 

    | TLS Protocol Version | TLS Cipher Suites |
    | -- | -- |
    | Protocol-TLSv1.2 | ECDHE-ECDSA-AES128-GCM-SHA256<br> ECDHE-ECDSA-AES256-GCM-SHA384<br> ECDHE-RSA-AES128-GCM-SHA256<br> ECDHE-RSA-AES256-GCM-SHA384<br>
