## Filters

Collection endpoints have optional filter options to scope down the results. The filters are passed in as URL parameters, like `?parameter=value&other_parameter=value`.

Pluralized filters, e.g. `subject_ids`, can take in one or more values in the format of a comma-delimited string:

* A single-member `subject_ids` request: `...?subject_ids=8`
* A multiple-member `subject_ids` request: `...?subject_ids=8,16,64`
