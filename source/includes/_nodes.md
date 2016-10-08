# Nodes

There are ten nodes installed at Volcán Masaya, two at the very bottom right by the live lava lake, three halfway into the crater on what is known as level 1, and five around the perimeter of the crater rim of the Santiago Crater that houses the lava lake.

A node is a representation of a collection of sensors. Each node has a GPS location that enables you to pin point it on a map. Installed on every node are three sensor probes that collect a total of five different types of data [see Data Types](#data-types).

Data samples are commissioned by a node twice per hour to preserve battery life, for a total of 2,400 new data samples per 24 hours.

Every node also reports its latest battery life, and its current `status`. The `status` is either `ONLINE` or `OFFLINE`. A node is considered `OFFLINE` when no sensor is sending valid data to the API.

Finally, each node have a name, `N1` through `N10` following the scientific team that installed them inside the volcano, and are referred to in the scientific papers the team is creating following the expedition.

## [ `/nodes` ] Get All Nodes

> GET All Nodes

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/nodes
-X GET
```

> Response Object Array[ JSON ]

```json
[
	{
		"id": "c147ece0-8679-11e6-a353-2f6c041e2491",
		"name": "N9",
		"description": null,
		"location": null,
		"status": "OFFLINE",
		"created_at": "2016-08-07T00:51:40.000Z",
		"updated_at": "2016-09-29T19:41:07.065Z",
		"volcano_id": "35dc3e90-8679-11e6-bda3-ef77801087ee",
		"sensors": [
			{
				"id": "c15a6370-8679-11e6-a353-2f6c041e2491",
				"status": "OFFLINE",
				"url": "/sensors/c15a6370-8679-11e6-a353-2f6c041e2491",
				"type": "carbon dioxide concentration"
			},
			{
				"id": "c159c730-8679-11e6-a353-2f6c041e2491",
				"status": "OFFLINE",
				"url": "/sensors/c159c730-8679-11e6-a353-2f6c041e2491",
				"type": "battery"
			},
			{
				"id": "c159ee40-8679-11e6-a353-2f6c041e2491",
				"status": "OFFLINE",
				"url": "/sensors/c159ee40-8679-11e6-a353-2f6c041e2491",
				"type": "hydrogen sulfide concentration"
			},
			...
		]
	},
	...
]
```

This end-point returns all nodes inside the API as an array of JSON objects.

## [ `/nodes/{node_id}` ] Get Single Node

> GET a Single Node

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/nodes/c147ece0-8679-11e6-a353-2f6c041e2491
-X GET
```

> Response Object JSON

```json
{
	"id": "c147ece0-8679-11e6-a353-2f6c041e2491",
	"name": "N9",
	"description": null,
	"location": null,
	"status": "OFFLINE",
	"created_at": "2016-08-07T00:51:40.000Z",
	"updated_at": "2016-09-29T19:41:07.065Z",
	"volcano_id": "35dc3e90-8679-11e6-bda3-ef77801087ee",
	"sensors": [
		{
			"id": "c15a6370-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c15a6370-8679-11e6-a353-2f6c041e2491",
			"type": "carbon dioxide concentration"
		},
		{
			"id": "c159c730-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c159c730-8679-11e6-a353-2f6c041e2491",
			"type": "battery"
		},
		{
			"id": "c159ee40-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c159ee40-8679-11e6-a353-2f6c041e2491",
			"type": "hydrogen sulfide concentration"
		},
		{
			"id": "c15a6371-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c15a6371-8679-11e6-a353-2f6c041e2491",
			"type": "temperature"
		},
		{
			"id": "c15a6372-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c15a6372-8679-11e6-a353-2f6c041e2491",
			"type": "pressure"
		},
		{
			"id": "c15c5f40-8679-11e6-a353-2f6c041e2491",
			"status": "OFFLINE",
			"url": "/sensors/c15c5f40-8679-11e6-a353-2f6c041e2491",
			"type": "humidity"
		}
	]
}
```

This end-point returns a single node given its unique `id`.
