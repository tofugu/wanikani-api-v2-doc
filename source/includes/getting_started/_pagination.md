## Pagination

### Collection Size

By default, the maximum number of resources returned for collection endpoints is 500. Some endpoints may return a different size — `reviews` and `subjects` have a maximum size of 1,000.

Any collection response has the per-page count in the `pages.per_page` attribute. Those same responses have a `total_count` attribute, too. That is a count of all resources available within the [specified scope](#filters), **not** limited to pagination.

### Pagination in Action

When there are more resources to return than the per-page limit, we use a [cursor-based pagination](https://www.sitepoint.com/paginating-real-time-data-cursor-based-pagination/) scheme to move through the pages of results. We use the `id` of a resource as the cursor.

To make it super simple, collections have the following nested within a `pages` attribute:

Attribute | Data Type | Description
--------- | --- | -----------
`next_url` | String | The URL of the next page of results. If there are no (more) results, the value is `null`.
`previous_url` | String | The URL of the previous page of results. If there are no results at all or no previous page to go to, the value is `null`.
`per_page` | Integer | Maximum number of resources delivered for this collection.

<aside class="notice">
Pro tip: the first page has no previous page, and the last page has no next page.
</aside>

The previous page of results can be requested by passing in the `page_before_id` parameter, with the value being the `id` you want to look before. Similar logic applies for the next page. Pass in the `page_after_id` parameter with with the `id` you want to look after.

If a cursor is outside the range of `id`s for the collection, an empty result set is returned for `data`.

#### Example

Let’s say there are four resources with IDs of 1, 2, 3, 4.

* If we make a request with `...?page_after_id=2`, then we'll get resources with IDs&nbsp;3&nbsp;and&nbsp;4.
* If we make a request with `...?page_before_id=3`, then we'll get resources with IDs&nbsp;1&nbsp;and&nbsp;2.
* If we make a request with `...?page_after_id=5`, then we'll get a collection with an empty&nbsp;`data`&nbsp;field.
