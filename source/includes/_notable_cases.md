# Notable Cases

## User Resets

A user has the option to reset their account to a target level below their current level.

When the user resets all subjectable resources (`assignment`, `review_statistic`, and `study_material`) at or above the user’s target level will have their fields set to the defaults and the `updated_at` timestamp will be touched.

User resets can be inferred from the [Level Progressions](#level_progressions) endpoint. The latest resource with a timestamp on the `abandoned_at` field means the user has reset. The next `level_progression` object in the sequence is the user's new level.
