# Authentication

Soccer Football info REST api authenticates via Access Token.

The modes differ if you use the direct API or via RapidAPI.   
Here's how to do it:

### Authentication with direct API 

The main URL is: `https://api.soccerfootball.info`

You must enter the **`t=`** parameter with your access token for each endpoint to work.  
For example: 

```text
https://api.soccerfootball.info/endpoint/url?t=TOKEN
```

#### Header on response

On response there is some header that you can use to check API status

* `X-Rate-Limit-Limit`: the rate limit ceiling for that given endpoint
* `X-Rate-Limit-Remaining`: the number of requests left for the hour window
* `X-Rate-Limit-Reset`: the remaining window before the rate limit resets, in UTC epoch seconds

### Authentication with RapidAPI 

The main URL is: `https://soccerfootballinfo.rapidapi.com`

You must pass two custom header to endpoint with your token and api host.

* `x-rapidapi-host` : the api hostname is always `soccerfootballinfo.rapidapi.com`
* `x-rapidapi-key`  : your API token

For example:

```text
GET https://soccerfootballinfo.rapidapi.com/endpoint

x-rapidapi-host: soccerfootballinfo.rapidapi.com
x-rapidapi-key: TOKEN
```

#### Header on response

Ogni chiamata se risponderà 200 vi fornirà negli header le seguenti informazioni:

* `x-ratelimit-request-limit`: The number of requests the plan you are currently subscribed to allows you to make, before incurring overages
* `x-ratelimit-requests-remaining`: The number of requests remaining before you reach the limit of requests your application is allowed to make, before experiencing overage charges.

more info [here](https://docs.rapidapi.com/docs/headers-sent-by-api-proxy)

{% hint style="info" %}
You can limit your token by IP from RapidApi Dashboard or if you have a directly subscribe write a mail to [limit@soccerfootball.info](mailto:limit@soccerfootball.info) with your token and the IP.
{% endhint %}



