## Response Structure

We return JSON from all the API endpoints, even when an error occurs.

There are two main structures we return: resources and collections. Singular resource endpoints deliver information about a single entity, such as an assignment or subject. Collections contain summary data about a bunch of resources, and also include each of the resources.

There's a third type of structure that's less common: a report. Reports summarize disparate or novel information into a single place, and don't follow the same structure as collections.

> Resources follow the pattern:

```
{
  "id": <integer>,
  "object": <string>,
  "url": <string>,
  "data_updated_at": <date>,
  "data": <object>
}
```

> And collections look like:

```
{
  "object": <string>,
  "url": <string>,
  "pages": {
    "next_url": <string_or_null>,
    "previous_url": <string_or_null>,
    "per_page": <integer>
  },
  "total_count": <integer>,
  "data_updated_at": <date_or_null>,
  "data": <array_of_objects>
}
```

All of the responses have a few shared, high-level attributes: `object`, `url`, `data_updated_at`, and `data`.

Attribute | Description
--------- | -----------
`object` | The kind of object returned. See the [object types section](#object-types) below for all the kinds.
`url` | The URL of the request. For collections, that will contain all the filters and options you've passed to the API. Resources have a single URL and don't need to be filtered, so the URL will be the same in both resource and collection responses.
`data_updated_at` | For collections, this is the timestamp of the most recently updated resource in the [specified scope](#filters) and is not limited by pagination. If no resources were returned for the specified scope, then this will be `null`. For a resource, then this is the last time that particular resource was updated.
`data` | For collections, this is going to be the resources returned by the specified scope. For resources, these are the attributes that are specific to that particular instance and kind of resource.


### Object Types

Every successful API response contains an `object` attribute that tells you which kind of thing you're getting. As mentioned before, there are two object types that return information on many different resources:

* `collection`
* `report`

The following are singular resources:

* `assignment`
* `kana_vocabulary`
* `kanji`
* `level_progression`
* `radical`
* `reset`
* `review_statistic`
* `review`
* `spaced_repetition_system`
* `study_material`
* `user`
* `vocabulary`


### Data Types

We stick to the common JSON data types in our responses: strings, integers, booleans, arrays, and objects. We follow the Javascript standard for date formatting, returning them in [ISO 8601](https://xkcd.com/1179/) format, rounded to the microsecond.
