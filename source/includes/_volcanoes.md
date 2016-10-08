# Volcanoes

## Get all Volcanoes

> Request All Volcanoes

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/volcanoes
-X GET 
```

> Response Object Array[ JSON ]

```json
[
	{
		"id": "35dc3e90-8679-11e6-bda3-ef77801087ee",
		"name": "Masaya",
		"description": "This is the world's biggest, baddest, most evil volcano.",
		"location": [
			11.9853183,
			-86.1783429
		],
		"status": "OFFLINE",
		"created_at": "2016-09-29T19:16:23.419Z",
		"updated_at": "2016-10-07T07:43:05.015Z",
		"nodes": [
			{
				"id": "c5e39fa0-867a-11e6-a353-2f6c041e2491",
				"url": "/nodes/c5e39fa0-867a-11e6-a353-2f6c041e2491"
			},
			{
				"id": "c147ece0-8679-11e6-a353-2f6c041e2491",
				"url": "/nodes/c147ece0-8679-11e6-a353-2f6c041e2491"
			},
			{
				"id": "76309900-8679-11e6-a353-2f6c041e2491",
				"url": "/nodes/76309900-8679-11e6-a353-2f6c041e2491"
			},
			...
		]
	}
]
```

## Get single Volcano
