# Errors

There is some possibile errors:

## \#404

_Not Found error_. The endpoint is missing or it has been deleted. 

```javascript
{
	"status": 404,
	"errors": [
		{
			"code" : 6,
			"message" : "Not Found"
		}
	],
  	"pagination": [],
  	"result": []
}
```

## \#400

_Bad Request._ Missing some variable in endpoint. Only one error at time

```javascript
{
	"status": 400,
	"errors": [
		{
			"code" : 1,
			"message" : "Missing XXX param"
		}
	],
  	"pagination": [],
  	"result": []
}
```

## \#401

_Unauthorized._ Your token don't have enough of privileges to access at this endpoint or is suspended/invalid

```javascript
{
	"status": 401,
	"errors": [
		{
			"code" : 2,
			"message" : "Token is invalid"
		},
		{
			"code" : 3,
			"message" : "Token is suspended"
		},
		{
			"code" : 4,
			"message" : "Token does not have permission"
		},
		{
			"code" : 5,
			"message" : "Token IP is invalid"
		}
	],
  	"pagination": [],
  	"result": []
}
```

## \#429

_Too many requests._ Your token do too many requests due your plan limitation. Need to wait next hour

```javascript
{
	"status": 429,
	"errors": [
		{
			"code" : 7,
			"message" : "Too many requests"
		}
	],
  	"pagination": [],
  	"result": []
}
```

