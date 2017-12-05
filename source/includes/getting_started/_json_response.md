## JSON Response

> Collections generally follow the pattern:

```
{
  object: :string,
  url: :string,
  pages: {
    next_url: :string_or_null,
    previous_url: :string_or_null,
    per_page: :integer
  },
  total_count: :integer,
  data_updated_at: :date,
  data: :array_of_objects
}
```

> The `data` is a collection of resources as patterned:

```
{
  id: :integer,
  object: :string,
  url: :string,
  data_updated_at: :date,
  data: :object
}
```

> Here, `data` returns the specific fields for that kind of resource.

WaniKani API is structured to be RESTful.

Details on some of the fields:

* `id` — Unique identifier of the resource.
* `url` — URL of the request
* `data_updated_at` — If a response from a collection endpoint, then the latest updated timestamp of all the resources available within the [specified scope](#filters), not limited to pagination. If a response from a resource endpoint, then the updated timestamp of the resource object.
* `data` — The requested resource(s).

Rest of the fields are discussed below.

### Object Types

Each resource and collection contains an `object` key with an identifying value.

The API has the following high level objects:

* `collection`
* `report`

The purpose of `report` objects is to provide summarize data from various parts of the application. Note `report` do not include `id` in the body.

And a list of specific resource objects:

* `assignment`
* `level_progression`
* `kanji`
* `radical`
* `review`
* `review_statistic`
* `study_material`
* `user`
* `vocabulary`

### Collection Size

By default the number of resources returned for all collection endpoints is set to a maximum of 1000. Some endpoints may return a different size. The value can be found on `pages.per_page`.

The `total_count` field is a count of all resources available within the [specified scope](#filters), not limited to pagination.

### Pagination

To help with paging through results, a couple pieces of information is provided on collections:

* `pages.next_url` — A url if the next page exists. Else the value is `null`.
* `pages.previous_url` — A url if the previous page exists. Else the value is `null`.
* `pages.per_page` — Maximum number of resources delivered for this collection.

<aside class="notice">
Protip: the first page has no previous page, and the last page has no next page.
</aside>

WaniKani API uses a cursor-based pagination scheme, with the `id` of a resource acting as the cursor.

The previous page of results can be requested by passing in the `page_before_id` parameter, with the value being the `id` you want to look before. Similar logic applies for the next page. Pass in the `page_after_id` parameter with with the `id` you want to look after.

If a cursor is outside the range of `id`s for the collection, an empty result set is returned for `data`.

Since it’s slightly ambiguous, here is a simple example:

Let’s say there are four Subject resources with `id` of 1, 2, 3, 4.

If a request to `/api/v2/subjects/?page_after_id=2` is initiated, then the response will have resources of `id` 3 and 4.

If a request to `/api/v2/subjects/?page_before_id=3` is initiated, then the response will have resources of `id` 1 and 2.

If a request to `/api/v2/subjects/?page_after_id=5` is initiated, then the collection will yield empty result set.

### Resource Ordering in Collections

Resources in a collection are ordered by ascending `created_at`.

### Timestamps

All timestamps are rendered in [ISO8601](https://xkcd.com/1179/) to the microsecond.
