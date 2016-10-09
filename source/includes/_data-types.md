# Data Types

> Request All Data-Types

```shell
volcanoes$ curl https://masaya-web.run.aws-usw02-pr.ice.predix.io/data_types
-X GET
```

> Response Object Array[ JSON ]

```json
[
	{
		"id": "35dcb3c0-8679-11e6-bda3-ef77801087ee",
		"type": "temperature",
		"si_unit": "celcius",
		"type_id": "TCA"
	},
	{
		"id": "35dcb3c1-8679-11e6-bda3-ef77801087ee",
		"type": "pressure",
		"si_unit": "pascal",
		"type_id": "PA"
	},
	{
		"id": "35dcb3c2-8679-11e6-bda3-ef77801087ee",
		"type": "humidity",
		"si_unit": "relative humidity",
		"type_id": "HUMA"
	},
	{
		"id": "35dcdad0-8679-11e6-bda3-ef77801087ee",
		"type": "carbon dioxide concentration",
		"si_unit": "ppm",
		"type_id": "GP_CO2"
	},
	{
		"id": "35dcdad1-8679-11e6-bda3-ef77801087ee",
		"type": "hydrogen sulfide concentration",
		"si_unit": "ppm",
		"type_id": "GP_H2S"
	},
	{
		"id": "35dcdad2-8679-11e6-bda3-ef77801087ee",
		"type": "battery",
		"si_unit": "percentage",
		"type_id": "BAT"
	}
]
```

There are five main data types collected by the sensors. Each data type has a unique `id`, `type`, `si_unit`, and `type_id`. The information provided by `type_id` stems from the sensor manufacturer, [Libelium](https:www.libelium.com), and is useful if you need to get in touch with them regarding a specific sensor type.

The types of data currently collected by the sensors installed inside Volcán Masaya are

Data Type | SI Unit | Description
-------------- | -------------- | --------------
Carbon dioxide (CO2) | PPM | Measured in [parts per million](https://en.wikipedia.org/wiki/Parts-per_notation)
Hydrogen Sulfide (H2S) | PPM | Measured in [parts per million](https://en.wikipedia.org/wiki/Parts-per_notation)
Temperature | Degrees Celsius | Measured in degrees [Celsius](https://en.wikipedia.org/wiki/Celsius)
Atmospheric Pressure | Pascal | Measured in [Pascal](https://en.wikipedia.org/wiki/Pascal_(unit))
Relative Humidity | Percentage | Measured in [partial pressure ratios](https://en.wikipedia.org/wiki/Relative_humidity)

A data type has the following attributes

Attribute | Type | Description |
-------------- | -------------- | -------------- |
`id` | `string` | Unique data-type `id` |
`type` | `string` | The type of data represented, e.g. temperature |
`si_unit` | `string` | SI unit of the data type, e.g. degrees Celsius |
`type_id` | `string` | A unique manufacturer string, e.g. TCA |
