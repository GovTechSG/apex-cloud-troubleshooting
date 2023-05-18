# Network connectivity issues

- [General network issues](#general-network-issues)
- [SSL/TLS issues](#ssltls-issues)

## General network issues

**Solution**

To diagnose any network issues, you can perform a network connectivity test on your server. This test should be performed from the same zone, either **internet** or **intranet**, from which you are making API requests.

There are two methods to perform the network connectivity test:

- [Option 1: Test using cURL](#test-using-the-terminal-with-curl)
- [Option 2: Test using a browser](#test-using-a-browser)

If at least one of the testing methods is successful, it indicates that the network connectivity is working as expected.

### Option 1: Test using cURL

Select the appropriate environment in the tabs below to view the sample code to test the network connectivity using cURL.

<!-- tabs:start -->
#### **Staging Intranet**

On an intranet machine, use the sample code below.

```
curl -kvv https://gw-stg.int.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![staging intranet with curl](/images/network-curl-staging-intranet.png)

#### **Staging Internet**

On an internet machine, use the sample code below.

```
curl -kvv https://public-stg.api.gov.sg/healthcheck
```

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![staging internet with curl](/images/network-curl-staging-internet.png)

#### **Production Intranet**

On an intranet machine, use the sample code below.

```
curl -kvv https://gw.int.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

![production intranet with curl](/images/network-curl-prod-intranet.png)

#### **Production Internet**

On an internet machine, use the sample code below.

```
curl -kvv https://public.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

![production internet with curl](/images/network-curl-prod-internet.png)

<!-- tabs:end -->

### Option 2: Test using a browser

Select the appropriate environment in the tabs below to view the sample code to test the network connectivity using a browser.

<!-- tabs:start -->

#### **Staging Intranet**

In your browser, open this URL: https://gw-stg.int.api.gov.sg/healthcheck

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![staging intranet with browser](/images/network-browser-staging-intranet.png)

#### **Staging Internet**

In your browser, open this URL: https://public-stg.api.gov.sg/healthcheck

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![production internet with curl](/images/network-browser-staging-internet.png)

#### **Production Intranet**

In your browser, open this URL: https://gw.int.api.gov.sg/healthcheck

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![production internet with curl](/images/network-browser-prod-intranet.png)

### **Production Internet**

In your browser, open this URL: https://public.api.gov.sg/healthcheck 

The connection is successful when an **ok status** is returned as shown in the screenshot below.

![production internet with curl](/images/network-browser-prod-internet.png)


<!-- tabs:end -->

## SSL/TLS issues

[SSL/TLS issues](/snippets/tls-support.md ':include')