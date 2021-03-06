## API Documentation

API v1.

---


### Common Response Fields

All responses will include these common fields -

| Term | Explanation |
|-----------|--------------|
|`status`| HTTP status code.|
|`requestLocation`| Location where request was made.|
|`developerMessage`| Verbose for debugging. Set only if there is an error.|
| `userMessage`| Error message for user.|
|`errorCode`| Platform specific error code.|

Example -
```json
{
	"status": 200,
	"requestLocation": "/api/v1/g"
}
```
```json
{
	"status": 500,
	"requestLocation": "/api/v1/g",
	"developerMessage": "URLOpen: Timeout",
	"userMessage": "Server problem, please try again later.",
	"errorCode": "500-004"
}
```

* ### Getting Audio from Video ID

	* **Type:** `GET`
	* **Location:** `/api/v1/g`
	* **Parameters**:

	| Term | Explanation |
	|-----------|--------------|
	|`url`| Encrypted URL as recieved from search.|

	Example -
	```json
	{
		"url": "fajgkwhgfaykuegwrkagekwugfayegvfukyahwegyfkuasdafsdfsdf"
	}
	```

	* **Response**:

	| Term | Explanation |
	|-----------|--------------|
	|`url`| URL to download the song from.|

	Example -
	```json
	{
		"url": "/api/v1/d?url=fSR3dG4kPCIkanZasdasdasdasdasfasfasdfasfasdas"
	}
	```

* ### Getting Youtube Search Results

	* **Type**: `GET`
	* **Location**: `/api/v1/search`
	* **Parameters**:

	| Term | Explanation |
	|-----------|--------------|
	|`q`| Search query.|

	Example -
	```json
	{
		"q": "Bass%20Rani"
	}
	```

	* **Response**:

	| Term | Explanation |
	|-----------|--------------|
	|`metadata`| Data about fetched data. <br/>&nbsp;&nbsp;&nbsp;&nbsp;`q`: Searched query.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`count`: Numner of results returned.|
	|`results`| Actual result set contains a list of items with following attributes : <br/>&nbsp;&nbsp;&nbsp;&nbsp;`get_url`: URL to get song from.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`title`: Title of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`id`: Youtube ID of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`length`: Length of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`thumb`: Link to video thumbnail.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`time`: Time since upload. e.g. `3 years ago`.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`uploader`: Youtube uploader ID.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`views`: View count for the video in comma separated number format.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`description`: Video description as on Youtube.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`suggest_url`: URL to get suggested songs from.|

	Example -
	```json
	{
		"metadata": {
			"q": "Bass%20Rani",
			"count": 3
		},
		"results" : [
			{
				"get_url": "/api/v1/g?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
				"id": "slNebO7Yips",
				"length": "4:34",
				"thumb": "http://img.youtube.com/vi/slNebO7Yips/0.jpg",
				"time": "10 months ago",
				"title": "Nucleya - BASS Rani - Aaja feat Avneet Khurmi &amp; Guri Gangsta",
				"uploader": "NUCLEYA",
				"views": "1,078,918",
				"description": "Some Description <strong>MAY</strong> contain HTML stuff",
				"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
			},
			{
				"get_url": "/api/v1/g?url=fSRrZiQ8IiRmc1RJOFJbTXl6eSQuIiR2a3ZuZyQ8IiROY3dwaSJJY3ljZWpjIkh2IkN4cGdndiJNand0b2sifiJQV0VOR1tDIn4iRENVVSJUQ1BLIn4iSHdubiJDbmR3byR/",
				"id": "dqRG6PYKwxw",
				"length": "3:35",
				"thumb": "http://img.youtube.com/vi/dqRG6PYKwxw/0.jpg",
				"time": "10 months ago",
				"title": "Laung Gawacha Ft Avneet Khurmi | NUCLEYA | BASS RANI | Full Album",
				"uploader": "Lyrics Arena",
				"views": "575,811",
				"description": "Some Description <strong>MAY</strong> contain HTML stuff",
				"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
			},
			{
				"get_url": "/api/v1/g?url=fSRrZiQ8IiR5bll1S0phZFdNVyQuIiR2a3ZuZyQ8IiRQV0VOR1tDIi8iQ0NMQyJ+IkRDVVUiVENQSyJ+IlFISEtFS0NOIkpTIkNXRktRIn4kfw==",
				"id": "wlWsIH_bUKU",
				"length": "4:35",
				"thumb": "http://img.youtube.com/vi/wlWsIH_bUKU/0.jpg",
				"time": "10 months ago",
				"title": "NUCLEYA - AAJA | BASS RANI | OFFICIAL HQ AUDIO |",
				"uploader": "Prasad Kedar",
				"views": "1,862,495",
				"description": "Some Description <strong>MAY</strong> contain HTML stuff",
				"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
			}
		]
	}
	```

* ### Getting Trending Songs

	* **Type**: `GET`
	* **Location**: `/api/v1/trending`
	* **Parameters**:

	| Term | Explanation |
	|------|--------------|
	|`number`| Max number of results to get in each playlist. Defaults to 25.|
	|`type`| Playlist type names separated by comma(s). Defaults to `popular`.|
	|`offset`| Number of items to skip before returning the results in each playlist. Defaults to 0. |

	* **Response**

	| Term | Explanation |
	|-----------|--------------|
	|`metadata`| Data about fetched data.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`count`: Number of results returned.|
	|`results`| Actual result set contains a list of items with following attributes : <br/>&nbsp;&nbsp;&nbsp;&nbsp;`get_url`: URL to get song from.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`id`: Youtube ID of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`title`: Title of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`length`: Length of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`thumb`: Link to video thumbnail.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`uploader`: Youtube uploader ID.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`views`: View count for the video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`description`: Video description as on Youtube.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`suggest_url`: URL to get suggested songs from.|

	Example -
	```json
	{
		"metadata": {
			"count": "2",
			"type": "popular,indian",
			"offset": "1"
		},
		"results" : {
			"popular": [
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"id": "slNebO7Yips",
					"length": "4:34",
					"thumb": "http://img.youtube.com/vi/slNebO7Yips/0.jpg",
					"title": "Nucleya - BASS Rani - Aaja feat Avneet Khurmi &amp; Guri Gangsta",
					"uploader": "NUCLEYA",
					"views": "1,078,918",
					"description": "Some Description <strong>MAY</strong> contain HTML stuff",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				},
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"id": "slNebO7Yips",
					"length": "4:34",
					"thumb": "http://img.youtube.com/vi/slNebO7Yips/0.jpg",
					"title": "Nucleya - BASS Rani - Aaja feat Avneet Khurmi &amp; Guri Gangsta",
					"uploader": "NUCLEYA",
					"views": "1,078,918",
					"description": "Some Description <strong>MAY</strong> contain HTML stuff",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				}
			],
			"indian": [
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiRmc1RJOFJbTXl6eSQuIiR2a3ZuZyQ8IiROY3dwaSJJY3ljZWpjIkh2IkN4cGdndiJNand0b2sifiJQV0VOR1tDIn4iRENVVSJUQ1BLIn4iSHdubiJDbmR3byR/",
					"id": "dqRG6PYKwxw",
					"length": "3:35",
					"thumb": "http://img.youtube.com/vi/dqRG6PYKwxw/0.jpg",
					"title": "Laung Gawacha Ft Avneet Khurmi | NUCLEYA | BASS RANI | Full Album",
					"uploader": "Lyrics Arena",
					"views": "575,811",
					"description": "Some Description <strong>MAY</strong> contain HTML stuff",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				},
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiRmc1RJOFJbTXl6eSQuIiR2a3ZuZyQ8IiROY3dwaSJJY3ljZWpjIkh2IkN4cGdndiJNand0b2sifiJQV0VOR1tDIn4iRENVVSJUQ1BLIn4iSHdubiJDbmR3byR/",
					"id": "dqRG6PYKwxw",
					"length": "3:35",
					"thumb": "http://img.youtube.com/vi/dqRG6PYKwxw/0.jpg",
					"title": "Laung Gawacha Ft Avneet Khurmi | NUCLEYA | BASS RANI | Full Album",
					"uploader": "Lyrics Arena",
					"views": "575,811",
					"description": "Some Description <strong>MAY</strong> contain HTML stuff",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				}
			]
		}
	}
	```

* ### Downloading from URL provided

	* **Type**: `GET`
	* **Location**: `/api/v1/d`
	* **Parameters**:

		| Term | Explanation |
		|------|--------------|
		|`url` | Encrypted URL as recieved from `/api/v1/g`|
	* **Response**: Audio file.

* ### Getting supported Playlists

	* **Type**: `GET`
	* **Location**: `/api/v1/playlists`
	* **Response**:

	| Term | Explanation |
	|------|--------------|
	|`metadata`| Contains following term:<br/>&nbsp;&nbsp;&nbsp;&nbsp;`count`: Number of playlists.|
	|`results`| List containing following dictionary:<br/>&nbsp;&nbsp;&nbsp;&nbsp;`playlist`: Name of playlist<br/>&nbsp;&nbsp;&nbsp;&nbsp;`url`: Playlist URL on Youtube|

	Example -
	```json
	{
		"metadata": {
			"count": "2"
		},
		"results": [
			{
				"playlist": "popular",
				"url": "https://www.youtube.com/playlist?list=PLFgquLnL59alCl_2TQvOiD5Vgm1hCaGSI"
			},
			{
				"playlist": "latest",
				"url": "https://www.youtube.com/playlist?list=PLFgquLnL59akA2PflFpeQG9L01VFg90wS'"
			}
		]
	}
	```

* ### Streaming content
	* **Type**: `GET`
	* **Location**: `/api/v1/stream`
	* **Parameters**:

		| Term | Explanation |
		|------|--------------|
		|`url`| Encoded URL as recieved from the search|

	* **Response**:


	| Term | Explanation |
	|------|--------------|
	|`status`| Status code |
	|`url`| Url to stream from |

	Example -
	```json
	{
		"status": 200,
		"url": "/api/v1/stream_handler?url=asfj2jJSAJDAJASKK898989"
	}
	```


* ### Getting related videos
	* **Type**: `GET`
	* **Location**: `/api/v1/suggest`
	* **Parameters**:

		| Term | Explanation |
		|------|-------------|
		|`url`| Encoded URL as recieved from search. |

	* **Response**:

	|`Term`| Explanation |
	|------|-------------|
	|`metadata`| Contains following terms:<br/>&nbsp;&nbsp;&nbsp;&nbsp;`count`: Number of results shown.|
	|`results`| Actual result set contains a list of items with following attributes : <br/>&nbsp;&nbsp;&nbsp;&nbsp;`get_url`: URL to get song from.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`id`: Youtube ID of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`title`: Title of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`length`: Length of video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`thumb`: Link to video thumbnail.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`uploader`: Youtube uploader ID.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`views`: View count for the video.<br/>&nbsp;&nbsp;&nbsp;&nbsp;`suggest_url`: URL to get suggested songs from.|

	Example -
	```json
	{
		"metadata": {
			"count": 2
		},
		"results": [
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"id": "slNebO7Yips",
					"length": "4:34",
					"thumb": "http://img.youtube.com/vi/slNebO7Yips/0.jpg",
					"title": "Nucleya - BASS Rani - Aaja feat Avneet Khurmi &amp; Guri Gangsta",
					"uploader": "NUCLEYA",
					"stream_url": "/api/v1/stream?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"views": "1,078,918",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				},
				{
					"get_url": "/api/v1/g?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"id": "slNebO7Yips",
					"length": "4:34",
					"thumb": "http://img.youtube.com/vi/slNebO7Yips/0.jpg",
					"title": "Nucleya - BASS Rani - Aaja feat Avneet Khurmi &amp; Guri Gangsta",
					"stream_url": "/api/v1/stream?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8=",
					"uploader": "NUCLEYA",
					"views": "1,078,918",
					"suggest_url": "/api/v1/suggest?url=fSRrZiQ8IiR1blBnZFE5W2tydSQuIiR2a3ZuZyQ8IiRQd2VuZ3tjIi8iRENVVSJUY3BrIi8iQ2NsYyJoZ2N2IkN4cGdndiJNand0b2siKGNvcj0iSXd0ayJJY3BpdXZjJH8="
				}
		]
	}
	```
