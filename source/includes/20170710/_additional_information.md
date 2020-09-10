# Additional Information

## Spaced Repetition System

Our [spaced repetition systems](#spaced-repetition-systems) determine how subjects progress from being unavailable to users (locked) through complete memorization (burned). The [knowledge guide](https://knowledge.wanikani.com/wanikani/srs-stages/) has some good general information about how we use SRS in WaniKani.

A single spaced repetition system consists of `N` number of sequential stages. Each stage describes its position in the sequence as well as the time interval that’s used to determine when the subject will appear next in reviews.

Each system has the following common characteristics.

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
      <td style="text-align: right;">Unlocking stage</td>
      <td>0</td>
      <td>This is the initial stage for an assignment; it generally indicates the subject will appear in lessons.</td>
    </tr>
    <tr>
      <td style="text-align: right;">Starting stage</td>
      <td>1</td>
      <td>The minimum stage for a subject to appear in reviews.</td>
    </tr>
    <tr>
      <td style="text-align: right;">Passing stage</td>
      <td>Value from the starting stage position up to the burning stage position</td>
      <td>Reaching this milestone counts towards level progression and the unlocking of additional subjects.</td>
    </tr>
    <tr>
      <td style="text-align: right;">Burning stage</td>
      <td>N</td>
      <td>This is the stage when the subject is complete, exits out of reviews and is no longer tested.</td>
    </tr>
  </tbody>
</table>

As mentioned before, we use the SRS stages to calculate the time until the next review (the 'space' in the 'spaced-repetition').

* If the review goes well and there are no wrong answers, we move the assignment up to the next SRS stage. We make the assignment available 'interval' hours from now, at the top of the hour. For example: given an assignment at stage `1`, when we submit a correct answer at 3:31pm, the assignment would move to SRS stage `2` and become available for another review at 11:00pm.
* If there are wrong answers, we decrease the SRS stage based on the number of times it was wrong, and then again make it available according to the interval for that SRS stage.

## User Resets

Users have the option to reset their account to a target level at or below their current level.

Resets will show up in a variety of places. Explicit records will show up under [resets](#resets). They'll get a fresh [level progression](#level-progressions) for the target level of the reset, and the level progression for the level they abandoned gets an `abandoned_at` timestamp. Finally, the `assignments` and `review_statistics` for the affected levels will get set back to their default state, waiting to be unlocked or started, depending on the levels.
