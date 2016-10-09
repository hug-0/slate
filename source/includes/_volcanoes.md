# Volcanoes

Volcano resources contain the following attributes

Attribute | Type | Description |
-------------- | -------------- | -------------- |
`id` | `string` | Unique identifier for a volcano |
`name` | `string` | Name of the volcano |
`description` | `string` | A short description that describes the volcano |
`location` | `array[ number, number ]` | An array containing the GPS location of the volcano, `[ longitude,  latitude ]` of the volcano |
`status` | `string` | Current status of the volcano. `status` is either `ONLINE` or `OFFLINE`. A volcano is considered `OFFLINE` when no connected node is sending sensory data that can be properly interpreted |
`created_at` | `date` | The UTC timestamp when the volcano first came online |
`updated_at` | `date` | The UTC timestamp when the volcano was last updated. This property is updated anytime a node has sent new sensor data that can be properly interpreted |
`nodes` | `array[ JSON ]` | An array of nodes and their unique ids and short-form resource URI inside the API |

## [ `/volcanoes` ] Get all Volcanoes

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

Returns an array of all volcanoes inside the API.

## [ `/volcanoes/{id}` ] Get single Volcano

> Request Single Volcano

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/volcanoes/35dc3e90-8679-11e6-bda3-ef77801087ee
-X GET
```

> Response Object JSON

```json
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
```

Returns a single volcano given its unique `id` in JSON format.
