---
title: Open Volcano API

language_tabs:
- shell

toc_footers:
- <a href='#'>Sign Up for an API Key</a>
- <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
- volcanoes
- nodes
- sensors
- data-types

search: true
---

# Introduction

The Volcano API is organized around REST. The API has predictable resource-oriented URLs, and makes use of HTTP response codes to indicate errors. JSON is returned by all API responses, except for certain errors that are sent in plain text.

There are four top-level API resources

	1. `volcanoes`
	2. `nodes`
	3. `sensors`
	4. `data-types`

that in combination create a virtual representation of a connected volcano. The majority of the data exposed by these resources are data samples collected from the sensors installed inside Volcàn Masaya in Nicaragua, and are represented as time series data.

To learn more about each individual resource type and the types of data that are collected, please see the sub-headers below.

# Base URI

To call an API resource, use the base URI `https://masaya-web.run.aws-usw02-pr.ice.predix.io`.

# Authentication

The API is open for requests by default, and authentication is only required if `POST`, `PUT` or `PATCH` methods are required, such as when a new volcano is added, or if a new node of sensors is installed at an existing volcano resource.

Bear in mind that _all_ API requests must be made over HTTPS. Any calls made over HTTP will fail.

# Errors

Conventional HTTP response codes are used to indicate the success or failure of an API request. Codes in the `2XX` range indicate _success_, codes in the `4XX` range suggests an error caused due to incorrect information provided, and codes in the `5XX` range indicate a server-side error.

# Pagination

Some API resources support pagination to minimize browser load times, and to promote developers to specify in detail what they are looking for using query parameters in the API call. The query parameters are `timestamp_min` and `timestamp_max`, respectively. Each takes a UTC date string in the form of `YYYY-MM-DDTHH:MM:SS.XXXZ`, e.g. `2016-09-29T05:04:52.999Z`.
