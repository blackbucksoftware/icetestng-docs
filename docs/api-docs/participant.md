---
sidebar_position: 5
---

# Participant

## /music

The `/music` endpoint can be used to add or update music information for a specific entry.

```jsx title="POST /participant/music" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
    "token": "2KSZsnUN0jTOyCHj8M0/5w==",
	"testcode": "T1",
    "sta": 129,
    "music_url" : "https://open.spotify.com/playlist/0q47cFCoLmJPtbJYgXpsks",
    "music_notes" : "Start at short side.",
	"sandbox": false
}
```

```jsx title="Expected result"
{
	Entry updated.
}
```

## /entriesByEmail

Calling `/entriesByEmail` will return an array of STAs and their respective entries for a rider with a given email address.

```jsx title="POST /participant/entriesByEmail" showLineNumbers
{
	"competitionId": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
    "token": "2KSZsnUN0jTOyCHj8M0/5w==",
	"email": "test@mail.org",
	"sandbox": false
}
```

```jsx title="Expected result"
[
	{
		"testcode": "T7",
		"music_url": "",
		"lastname": "Doe",
		"competition": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
		"sta": 458,
		"phase": "PREL",
		"firstname": "Jane",
		"personid": "R19032800",
		"music_notes": ""
	},
	{
		"testcode": "V5",
		"music_url": "",
		"lastname": "Doe",
		"competition": "9ffa0058-35bf-433a-9d4db9cbffd54e52",
		"sta": 458,
		"phase": "PREL",
		"firstname": "Jane",
		"personid": "R19032800",
		"music_notes": ""
	}
]
```