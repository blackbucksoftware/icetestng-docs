---
sidebar_position: 1
---

# Overview

IceTest NG offers a [REST](https://www.techtarget.com/searchapparchitecture/definition/RESTful-API) API to exchange data with third party services. Typical use cases are signup systems that can send participant data to IceTest NG or Icelandic horse associations requesting results from IceTest NG. A wide range of further use cases is possible, and we encourage you to [get in touch](mailto:info@blackbuck.eu) if you are interested in accessing the API.


## Base URL

The base URL of the API is `https://api.icetestng.com/index.cfm/v1`. The full URL of a request consists of the base URL and the appended **resource** and **endpoint** information, for example `https://api.icetestng.com/index.cfm/v1/competition` or `https://api.icetestng.com/index.cfm/v1/test/list`. 

The documentation on available resources and endpoints will also mention the **HTTP verb** required for different requests.


## Authentication

All requests sent to the API need to provide a username and password according to the **Basic Authentication** scheme: an `Authorization` header starting with the word `Basic` followed by `username:password` in base64-encoded format.

```jsx
Authorization: Basic ZGVtbzpwQDU1dzByZA==
```

:::note

Usernames and passwords for use with the API are separate from login credentials for the IceTest NG application. Please [contact us](mailto:info@blackbuck.eu) if you need a username/password for the API.

:::

Most requests require an **authorization token** in addition to username and password. A token represents the permission given to a user to access a specific competition. A token can be retrieved via the API while creating a new competition, and will be sent as part of the payload when making requests.


## Payload

Data that is sent to the API is expected to be in JSON format:

```jsx title="GET /competition" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e50",
	"token": "YTvJF7YUxPyXMt/W1w6YcA==",
	"sandbox": true
}
```


## Environments

The API supports two environments, **production** and **sandbox**. While requests made to production are processed by the "live" IceTest NG system ([app.icetestng.com](https://app.icetestng.com)), requests in sandbox mode are going to the demonstration system available at [demo.icetestng.com](https://demo.icetestng.com) which is not connected to the outside world.

Send `"sandbox" : true` in a payload to direct your request to the demo system, otherwise it will go to the live system.


## Results

The IceTest NG API will return data in JSON format as well. For example, the answer to the request above could look like this:

```jsx title="Sample response from the API" showLineNumbers
{
	"ROWCOUNT": 1,
	"COLUMNS": [
		"ROWID",
		"COMPETITIONID",
		"WRCODE",
		"EVENTNAME",
		"EVENTFIRST",
		"EVENTLAST",
		"EVENTCOUNTRY",
		"ASSOCIATION",
		"LOCALE",
		"CHECKQ",
		"EMAIL",
		"SHAREDSECRET",
		"BFIN_ON",
		"CFIN_ON",
		"TICKER_STARTLIST",
		"ALLOW_SECRETARIES",
		"SET_DEFAULT_JUDGES",
		"TICKER_FINALRESULTS",
		"FIT_FINALS"
	],
	"DATA": {
		"ROWID": [
			309
		],
		"COMPETITIONID": [
			"9ffa0058-35bf-433a-9d4db9cbffd54e50"
		],
		"WRCODE": [
			""
		],
		"EVENTNAME": [
			"My Cool Event 25 ++"
		],
		"EVENTFIRST": [
			"April, 02 2020 00:00:00 +0200"
		],
		"EVENTLAST": [
			"April, 05 2020 00:00:00 +0200"
		],
		"EVENTCOUNTRY": [
			"DK"
		],
		"ASSOCIATION": [
			"DI"
		],
		"LOCALE": [
			"da_DK"
		],
		"CHECKQ": [
			0
		],
		"EMAIL": [
			""
		],
		"SHAREDSECRET": [
			""
		],
		"BFIN_ON": [
			0
		],
		"CFIN_ON": [
			0
		],
		"TICKER_STARTLIST": [
			"publish"
		],
		"ALLOW_SECRETARIES": [
			0
		],
		"SET_DEFAULT_JUDGES": [
			1
		],
		"TICKER_FINALRESULTS": [
			"automatic"
		],
		"FIT_FINALS": [
			0
		]
	}
}
```


