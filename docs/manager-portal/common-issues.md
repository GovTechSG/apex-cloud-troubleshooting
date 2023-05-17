# Common issues in the API Manager Portal

<!-- 
Cannot find APIs/APPs
How to request access to API
I am not able to edit the API
I noticed that my customized headers are missing after calling APEX Cloud
-->

### Issue: Cannot find APIs/APPs
<details><b><summary style="font-size:20px">Solution</b></summary>

Please ensure that you are managing the APIs or APPs at the correct environment/zone.

- [Staging (external): https://go.gov.sg/apex-stg](https://go.gov.sg/apex-stg)
- [Staging (internal): https://go.gov.sg/apex-int-stg](https://go.gov.sg/apex-int-stg)
- [Production (external): https://go.gov.sg/apex](https://go.gov.sg/apex)
- [Production (internal): https://go.gov.sg/apex-int](https://go.gov.sg/apex-int)

Once logged into the desired APEX Cloud API Manager Portal, please switch to the correct Organisation to view/manage the APIs or APPs.

![Image](./image/docs-home-chng-org.png)

</details>

<details><b><summary style="font-size:20px">As a consumer or developer, how to request API access?</b></summary>

If you are an existing APEX Cloud consumer, you may email the desired API's publisher and request for access to be given to the organisation which needs to access the API.

For new APEX Cloud consumers, please visit the [APEX Cloud Onboarding Guide](https://docs.developer.tech.gov.sg/docs/apex-cloud-onboarding/) for more information.

</details>

<details><b><summary style="font-size:20px">As an API publisher, I am not able to edit the API</b></summary>

An API in a published state cannot be modified. We recommend publishers to create a new API to upgrade the original API to it. If publishers was to unpublish the API to make any changes to it, this will cause the API to lost the API to APP relationship. This relationship can only be established again with the help of the consumer, without the API to APP linkage being re-establish API calls which requires inbound authentication on APEX Cloud will fail.

Therefore publisher are advice to use the [Update API](docs/publisher/update-api.md) workflow to make any changes to their API.
</details>

I noticed that my customized headers are missing after calling APEX Cloud

# I noticed that my customized headers are missing after calling APEX Cloud

API calls to APEX Cloud must conform to the regular expression `[-A-Za-z0-9]+` for any HTTP header names. HTTP Headers with names that do not conform to the expression `[-A-Za-z0-9]+` will be considered as invalid HTTP headers and will be dropped, in accordance to IM8 Cloud Security Section Para 1.7 S6.

![Image](./image/im8-header.png)

You may refer to: [https://intranet.mof.gov.sg/portal/IM/Themes/IT-Management/Cloud/Topics/Cloud-Security.aspx](https://intranet.mof.gov.sg/portal/IM/Themes/IT-Management/Cloud/Topics/Cloud-Security.aspx) for more information.