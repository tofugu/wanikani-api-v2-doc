# Additional Information

## Spaced Repetition System

[Spaced repetition systems](#spaced-repetition-systems) are what determines a subject progression. A subject progression means the lifecycle of going from unlocking, lessons, reviews, and completion (also known as "burning").

A spaced repetition system consists of N number of stages. And depending on the type of stage each is associated to a time interval. This time interval is what determines the earliest when a subject appears in reviews.

An assumption has been made that you are familiar with how the WaniKani and the spaced repetition systems work. The [knownledge guide](https://knowledge.wanikani.com/wanikani/srs-stages/) has some information if you need a refresher.

Each spaced repetition has the following common characteristics.

<table>
  <thead>
    <tr>
      <th>Special stage name</th>
      <th>Stage position/number</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th style="text-align: right;">Unlocking stage</th>
      <td>0</td>
      <td>This is the stage for lessons</td>
    </tr>
    <tr>
      <th style="text-align: right;">Starting stage</th>
      <td>1</td>
      <td>Minimum stage for reviews</td>
    </tr>
    <tr>
      <th style="text-align: right;">Passing stage</th>
      <td>Value between and including the starting stage and the burning stage</td>
      <td>Reaching this milestone contributes towards level progression and the unlocking of additional subjects.</td>
    </tr>
    <tr>
      <th style="text-align: right;">Burning stage</th>
      <td>N</td>
      <td>This is the stage when the subjected has been completed, exiting out of reviews and no longer being tested</td>
    </tr>
  </tbody>
</table>

As mentioned before we use the SRS stages to calculate the time until the next review (the 'space' in the 'spaced-repetition').

* If the review goes well and there are no wrong answers, we move the assignment up to the next SRS stage. We make the assignment available 'interval' hours from now, at the top of the hour. For example: given an assignment at stage `1`, when we submit a correct answer at 3:31pm, the assignment would move to SRS stage `2` and become available for another review at 11:00pm.
* If there are wrong answers, we decrease the SRS stage based on the number of times it was wrong, and then again make it available according to the interval for that SRS stage.

## User Resets

Users have the option to reset their account to a target level at or below their current level.

Resets will show up in a variety of places. Explicit records will show up under [resets](#resets). They'll get a fresh [level progression](#level-progressions) for the target level of the reset, and the level progression for the level they abandoned gets an `abandoned_at` timestamp. Finally, the `assignments` and `review_statistics` for the affected levels will get set back to their default state, waiting to be unlocked or started, depending on the levels.
