# List

{% api-method method="get" host="https://api.soccerfootball.info" path="/v1/countries/list" %}
{% api-method-summary %}
List of all countries
{% endapi-method-summary %}

{% api-method-description %}
This endpoint returns with all countries and the relented entries. You can use this call to get country code and use it in another endpoints
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-rapidapi-key" type="string" required=true %}
Your API token **`RAPIDAPI ONLY`**
{% endapi-method-parameter %}

{% api-method-parameter name="x-rapidapi-host" type="string" required=true %}
soccerfootballinfo.rapidapi.com **`RAPIDAPI ONLY`**
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="t" type="string" required=true %}
Your API Token **`DIRECT API ONLY`**
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "status":200,
   "errors":[],
   "pagination":[],
   "result":[
      {
         "code":"AF",  // unique country code
         "name":"Afghanistan",
         "timezones":[
            "UTC+04:30"
         ],
         "championships":0, 
         "managers":2,
         "players":13,
         "referees":0,
         "stadiums": 0,
         "teams":4
      },
		...
   ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Example of code for direct API

{% tabs %}
{% tab title="PHP" %}
```php
$url = 'https://api.soccerfootball.info/v1/countries/list/?t=TOKEN';

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_PROXY => null,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_ENCODING => "",
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 30,
    CURLOPT_CUSTOMREQUEST => "GET"
));

$response = curl_exec($curl);
$error = curl_error($curl);

curl_close($curl);

if (!$err) {
  $result = json_decode($response);
  print_r($result);
} else {
	echo "cURL Error:" . $err;
}
```
{% endtab %}

{% tab title="Javascript" %}
```python
fetch("https://api.soccerfootball.info/v1/countries/list/?t=TOKEN", {
	"method": "GET"
})
.then(response => {
	console.log(response);
})
.catch(err => {
	console.error(err);
});
```
{% endtab %}

{% tab title="NodeJS" %}
```javascript
const request = require('request');

const options = {
  method: 'GET',
  url: 'https://api.soccerfootball.info/v1/countries/list/?t=TOKEN'
};

request(options, function (error, response, body) {
	if (error) throw new Error(error);

	console.log(body);
});
```
{% endtab %}

{% tab title="Phyton" %}
```python
import requests

url = "https://api.soccerfootball.info/v1/countries/list/?t=TOKEN"

response = requests.get(url).json()

print(response)
```
{% endtab %}

{% tab title="cURL" %}
```bash

curl --request GET \
	--url 'https://api.soccerfootball.info/v1/countries/list/?t=TOKEN'

```
{% endtab %}

{% tab title="GO" %}
```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.soccerfootball.info/v1/countries/list/?t=TOKEN"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
{% endtab %}
{% endtabs %}

### Example of code for RapidAPI

{% tabs %}
{% tab title="PHP" %}
```php
$url = 'https://soccerfootballinfo.rapidapi.com/v1/countries/list';

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_PROXY => null,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_FOLLOWLOCATION => true,
    CURLOPT_ENCODING => "",
    CURLOPT_MAXREDIRS => 10,
    CURLOPT_TIMEOUT => 30,
    CURLOPT_CUSTOMREQUEST => "GET",
    CURLOPT_HTTPHEADER => [
		"x-rapidapi-host: soccerfootballinfo.rapidapi.com",
		"x-rapidapi-key: TOKEN"
	],
));

$response = curl_exec($curl);
$error = curl_error($curl);

curl_close($curl);

if (!$err) {
  $result = json_decode($response);
  print_r($result);
} else {
	echo "cURL Error:" . $err;
}
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
fetch("https://soccerfootballinfo.rapidapi.com/v1/countries/list/", {
	"method": "GET",
	"headers": {
		"x-rapidapi-key": "TOKEN",
		"x-rapidapi-host": "soccerfootballinfo.rapidapi.com"
	}
})
.then(response => {
	console.log(response);
})
.catch(err => {
	console.error(err);
});
```
{% endtab %}

{% tab title="NodeJS" %}
```javascript
const request = require('request');

const options = {
  method: 'GET',
  url: "https://soccerfootballinfo.rapidapi.com/v1/countries/list/",
  headers: {
   "x-rapidapi-key": "TOKEN",
	 "x-rapidapi-host": "soccerfootballinfo.rapidapi.com"
   useQueryString: true
  }
};

request(options, function (error, response, body) {
	if (error) throw new Error(error);

	console.log(body);
});
```
{% endtab %}

{% tab title="Phyton" %}
```python
import requests

url = "https://soccerfootballinfo.rapidapi.com/v1/countries/list"

headers = {
    "x-rapidapi-key": "TOKEN",
	  "x-rapidapi-host": "soccerfootballinfo.rapidapi.com"
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request GET \
	--url https://soccerfootballinfo.rapidapi.com/v1/countries/list \
	--header 'x-rapidapi-host: soccerfootballinfo.rapidapi.com' \
	--header 'x-rapidapi-key: TOKEN'
```
{% endtab %}

{% tab title="GO" %}
```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://soccerfootballinfo.rapidapi.com/v1/countries/list"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("x-rapidapi-key", "TOKEN")
	req.Header.Add("x-rapidapi-host", "soccerfootballinfo.rapidapi.com")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
{% endtab %}
{% endtabs %}

More example of code on [rapidAPI](https://rapidapi.com/api-sports/api/api-football?endpoint=apiendpoint_2d5d829b-5827-4f72-973f-32d3c297e957)

