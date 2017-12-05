## Filters

Collection endpoints have optional filter options to scope down the results. The filters are passed in as URL parameters, e.g `?parameter=value&other_parameter=value`.

Pluralize filters, for example `subject_ids`, can take in multiple values in the format of a comma-delimited string.

Example of a single member `subject_ids` request:

`...?subject_ids=8`

Example of a multiple member `subject_ids` request:

`...?subject_ids=8,16,64`
