---
sidebar_position: 2
---

# Competition

GET = 'view',
				PUT = 'save',
				POST = 'create'
## Create competition

```jsx title="POST /competition" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
	"nguser": "john.doe",
    "ngpass": "secretPassword",
	"sandbox": true
}
```

```jsx title="Expected result"
{
	"TOKEN": "2KSZsnUN0jTOyCHj8M0/5w=="
}
```



## /list

## /judges

## /tokenize

Use this function to add or update an API token. There's three use cases for this function:
1. An event has not been created through the API, but now you want to use the API to update the event.
2. You want to give an additional user access to an event through the API.
3. An existing token has been lost or compromised, and you need a new one.

The user who is requesting the new token needs to have EventAdmin permissions for the competition already.

```jsx title="POST /competition/tokenize" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
	"nguser": "john.doe",
    "ngpass": "secretPassword",
	"sandbox": true
}
```

```jsx title="Expected result"
{
	"TOKEN": "2KSZsnUN0jTOyCHj8M0/5w=="
}
```

## /participants

The `/participants` endpoint can be used to retrieve information on all participants currently registered for the competition specified.

```jsx title="GET /competition/participants" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
    "token": "2KSZsnUN0jTOyCHj8M0/5w==",
	"sandbox": false
}
```

```jsx title="Expected result"
[
	{
		"team": "",
		"name_horse": "Nátfari fra Langtved",
		"competition": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
		"feifid": "DK2007108500",
		"fullname": "Lara Manfrahs",
		"sta": 1,
		"class": "Erwachsene",
		"testlist": "Z1.F2,Z1.F2,Z1.FR1,Z1.T4,Z1.TR1"
	},
	{
		"team": "",
		"name_horse": "Náttfari fra Ll. Hafmey",
		"competition": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
		"feifid": "DK2009100141",
		"fullname": "Ann-Kristin Daus",
		"sta": 2,
		"class": "Erwachsene",
		"testlist": "SA.T7,ZA.T7"
	}
]
```
