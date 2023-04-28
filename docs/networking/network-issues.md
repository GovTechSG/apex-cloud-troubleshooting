# Troubleshooting network issues

To diagnose any network issues, you can perform a network connectivity test on your server. This test should be performed from the same zone, either **internet** or **intranet**, from which you are making API requests.

There are two methods to perform the network connectivity test:

- Using the command line with cURL
- Accessing through a browser

If at least one of the testing methods is successful, it indicates that the network connectivity is working as expected.

## Test using the command line with cURL

Select the appropriate environment in the tabs below to view the sample code to test the network connectivity using cURL.

<!-- tabs:start -->
### Staging Intranet

On an intranet machine, use the sample code below.

```
curl -kvv https://gw-stg.int.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 1/

### Staging Internet

On an internet machine, use the sample code below.

```
curl -kvv https://public-stg.api.gov.sg/healthcheck
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 2/

### Production Intranet

On an intranet machine, use the sample code below.

```
curl -kvv https://gw.int.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/ image 3 /

### Production Internet

On an internet machine, use the sample code below.

```
curl -kvv https://public.api.gov.sg/healthcheck 
```

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/ image 4 /

<!-- tabs:end -->

## Test using a browser

Select the appropriate environment in the tabs below to view the sample code to test the network connectivity using a browser.

<!-- tabs:start -->

### Staging Intranet

Use Browser to hit the url:
 https://gw-stg.int.api.gov.sg/healthcheck

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 1/

### Staging Internet

Use Browser to hit the url: 
https://public-stg.api.gov.sg/healthcheck

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 2/

### Production Intranet

Use Browser to hit the url: https://gw.int.api.gov.sg/healthcheck

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 3/

### Production Internet

Use Browser to hit the url: https://public.api.gov.sg/healthcheck 

The connection is successful when an **ok status**  is returned as shown in the screenshot below.

/image 4/


<!-- tabs:end -->


