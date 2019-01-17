# Additional Information

## SRS Stages

There are 10 stages in our spaced-repetition system. We start at `0`, which indicates that the subject hasn't been learned through lessons yet. When an assignment for a subject has obtained stage `5` once, the `assignment.passed_at` is touched, where it contributes towards level progress and can unlock additional assignments. Getting an assignment to stage `9` removes the timestamp on `assignment.available_at`, which removes the associated subject from the user's review queue — we think it's been firmly burned into memory at that point.

We use the SRS stages to calculate the time until the next review (the 'space' in the 'spaced-repetition').

* If the review goes well and there are no wrong answers, we move the assignment up to the next SRS stage. We make the assignment available 'interval' hours from now, at the top of the hour. For example: given an assignment at stage `1`, when we submit a correct answer at 3:31pm, the assignment would move to SRS stage `2` and become available for another review at 11:00pm.
* If there are wrong answers, we decrease the SRS stage based on the number of times it was wrong, and then again make it available according to the interval for that SRS stage.

The accelerated interval is used for the first two levels of assignments.

Stage | Name | Interval (hours) | Accelerated Interval (hours)
-- | -- | -- | --
0 | Initiate | 0 | 0
1 | Apprentice I | 4 | 2
2 | Apprentice II | 8 | 4
3 | Apprentice III | 23 | 8
4 | Apprentice IV | 47 | 23
5 | Guru I | 167 | 167
6 | Guru II | 335 | 335
7 | Master | 719 | 719
8 | Enlightened | 2,879 | 2,879
9 | Burned | n/a | n/a

For additional information regarding SRS stages please check out the [article on WaniKani Knowledge](https://knowledge.wanikani.com/wanikani/srs-stages/).

## User Resets

Users have the option to reset their account to a target level at or below their current level.

Resets will show up in a variety of places. Explicit records will show up under [resets](#resets). They'll get a fresh [level progression](#level-progressions) for the target level of the reset, and the level progression for the level they abandoned gets an `abandoned_at` timestamp. Finally, the `assignments` and `review_statistics` for the affected levels will get set back to their default state, waiting to be unlocked or started, depending on the levels.
