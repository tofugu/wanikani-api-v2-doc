## Filters

Collections have optional filters to help narrow the results returned. The filters are passed in as URL parameters, like `?parameter=value&other_parameter=value`.

Any time we take a query parameter that's listed as an array data type, we take that array as a comma delimited list of values. A single value is also valid.

So, if a collection endpoint takes `subject_ids` as an argument for filtering results, your requests might have the following formats:

* A single-member `subject_ids` request: `...?subject_ids=8`
* A multiple-member `subject_ids` request: `...?subject_ids=8,16,64`
