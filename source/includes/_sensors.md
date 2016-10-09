# Sensors

A sensor is installed on a node, and is responsible for sampling data at given time intervals, or when the node requests a new data reading of the surrounding environment. Currently, all sensors are provided by [Libelium](https:www.libelium.com), a Spanish manufacturer of Open Source hardware focused on data sampling.

Three separate sensor probes are installed on each node inside the volcano

Sensor | Type | Accuracy (95%) | Description |
-------------- | -------------- | -------------- | --------------
BME280 | Digital | ±1°C | This sensor samples relative humidity, temperature and atmospheric pressure |
INE20-CO2P-NCVSP | Near-Infrared (NDIR) | ±50ppm | This sensor samples Carbon Dioxide, measured in PPM
4-H2S-100 | Electro-chemical | ±0.1ppm | This sensor samples Hydrogen Sulfide

It takes up to 5 minutes for an accurate sampling to finish, where the Carbon Dioxide sensor is usually the cause for the time taken, as it has to be warmed up before any reading can take place.

Sensors contain the following attributes

Attribute | Type | Description |
-------------- | -------------- | -------------- |
`id` | `string` | Unique identifier for a sensor |
`description` | `string` | Short description of the sensor |
`data_frequency` | `string` | How often data is sampled in milliseconds |
`status` | `string` | Current status of the sensor. `status` is either `ONLINE` or `OFFLINE`. A sensor is considered `OFFLINE` when it is not sending sensory data that can be properly interpreted |
`created_at` | `date` | The UTC timestamp when the sensor first came online |
`updated_at` | `date` | The UTC timestamp when the sensor was last updated. This property is updated anytime it has sent new sensor data that can be properly interpreted |
`data_type_id` | `string` | Unique `id` to the data-type the sensor collects |
`node_id` | `string` | Unique `id` that describes which node the sensor is installed on |
`data_type` | `json` | A JSON object that described which [data-type](#data-types) the sensor collects |
`node` | `json` | A JSON object that describes which node and node resource URI the sensor is installed on |
`data_values` | `string` | A resource URI that points to the data values this sensor has collected over time |

For information on the type of data that is collected by the sensors, please see [data-types](#data-types).

## [ `/sensors` ] Get all Sensors


> Request all Sensors

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/sensors
-X GET
```

> Response Object Array[ JSON ]

```json
[
	{
		"id": "c15a6370-8679-11e6-a353-2f6c041e2491",
		"description": null,
		"data_frequency": 1800000,
		"status": "OFFLINE",
		"created_at": "2016-08-07T00:51:40.000Z",
		"updated_at": "2016-09-29T19:41:07.066Z",
		"data_type_id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
		"node_id": "c147ece0-8679-11e6-a353-2f6c041e2491",
		"data_type": {
			"id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
			"type": "carbon dioxide concentration",
			"si_unit": "ppm",
			"type_id": "GP_CO2",
			"url": "/data_types/35dcdad0-8679-11e6-bda3-ef77801087ee"
		},
		"node": {
			"id": "c147ece0-8679-11e6-a353-2f6c041e2491",
			"url": "/nodes/c147ece0-8679-11e6-a353-2f6c041e2491"
		},
		"data_values": "/sensors/c15a6370-8679-11e6-a353-2f6c041e2491/data_values"
	},
	{
		"id": "7635c920-8679-11e6-a353-2f6c041e2491",
		"description": null,
		"data_frequency": 1800000,
		"status": "OFFLINE",
		"created_at": "2016-08-03T04:39:25.000Z",
		"updated_at": "2016-09-29T20:13:52.793Z",
		"data_type_id": "35dcdad2-8679-11e6-bda3-ef77801087ee",
		"node_id": "762b8ff0-8679-11e6-a353-2f6c041e2491",
		"data_type": {
			"id": "35dcdad2-8679-11e6-bda3-ef77801087ee",
			"type": "battery",
			"si_unit": "percentage",
			"type_id": "BAT",
			"url": "/data_types/35dcdad2-8679-11e6-bda3-ef77801087ee"
		},
		"node": {
			"id": "762b8ff0-8679-11e6-a353-2f6c041e2491",
			"url": "/nodes/762b8ff0-8679-11e6-a353-2f6c041e2491"
		},
		"data_values": "/sensors/7635c920-8679-11e6-a353-2f6c041e2491/data_values"
	},
	...
]
```

Returns an array of all sensors connected to the API.

## [ `/sensors/{id}` ] Get single Sensor

> Request single Sensor

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/sensors
-X GET
```

> Response Object JSON

```json
{
	"id": "c15a6370-8679-11e6-a353-2f6c041e2491",
	"description": null,
	"data_frequency": 1800000,
	"status": "OFFLINE",
	"created_at": "2016-08-07T00:51:40.000Z",
	"updated_at": "2016-09-29T19:41:07.066Z",
	"data_type_id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
	"node_id": "c147ece0-8679-11e6-a353-2f6c041e2491",
	"data_type": {
		"id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
		"type": "carbon dioxide concentration",
		"si_unit": "ppm",
		"type_id": "GP_CO2",
		"url": "/data_types/35dcdad0-8679-11e6-bda3-ef77801087ee"
	},
	"node": {
		"id": "c147ece0-8679-11e6-a353-2f6c041e2491",
		"url": "/nodes/c147ece0-8679-11e6-a353-2f6c041e2491"
	},
	"data_values": "/sensors/c15a6370-8679-11e6-a353-2f6c041e2491/data_values"
}
```

Returns a single sensor given its unique `id`.

## [ `/sensors/{id}/data_values` ] Get Data Values from single Sensor

> Request Data Values from Single Sensor

```shell
volcano$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/sensors/c15a6370-8679-11e6-a353-2f6c041e2491/data_values
-X GET
```

> Response Object JSON

```json
{
	"data_type": {
		"id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
		"type": "carbon dioxide concentration",
		"si_unit": "ppm",
		"type_id": "GP_CO2"
	},
	"sensor": {
		"id": "c15a6370-8679-11e6-a353-2f6c041e2491",
		"description": null,
		"data_frequency": 1800000,
		"status": "OFFLINE",
		"created_at": "2016-08-07T00:51:40.000Z",
		"updated_at": "2016-09-29T19:41:07.066Z",
		"node_id": "c147ece0-8679-11e6-a353-2f6c041e2491"
	},
	"data_values": [
		{
			"id": "3a265440-868d-11e6-b9eb-2b0883ebdaeb",
			"value": null,
			"timestamp": "2016-08-28T21:35:14.000Z"
		},
		{
			"id": "277ea220-868d-11e6-b9eb-2b0883ebdaeb",
			"value": null,
			"timestamp": "2016-08-28T21:04:41.000Z"
		},
		{
			"id": "14cf75f0-868d-11e6-b9eb-2b0883ebdaeb",
			"value": null,
			"timestamp": "2016-08-28T20:34:42.000Z"
		},
		{
			"id": "14745da0-868d-11e6-b9eb-2b0883ebdaeb",
			"value": null,
			"timestamp": "2016-08-28T20:04:43.000Z"
		},
		{
			"id": "01ca6190-868d-11e6-b9eb-2b0883ebdaeb",
			"value": null,
			"timestamp": "2016-08-28T19:34:45.000Z"
		},
		...
	],
	"pagination": {
		"next": null,
		"prev": null
	}
}
```

Returns a JSON object of all data values sampled by a single sensor over time. This resource supports the query parameters `timestamp_min` and `timestamp_max` to limit or increase the number of data values returned by the resource. Pagination is also supported, if not all data values are returned from a simple `GET` request.

A data-value has the following attributes

Attribute | Type | Description |
-------------- | -------------- | -------------- |
`id` | `string` | Unique `id` of the data value |
`value` `number` | Sampled data value. `null` if data is corrupted or a physically impossible value |
`timestamp` | UTC timestamp, e.g. `"2016-08-28T19:34:45.000Z"` |

For readability, the key [sensor](#sensors) and [data-type](#data-types) attributes are also included in the response object.
