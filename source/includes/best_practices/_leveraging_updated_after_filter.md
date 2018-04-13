## Leveraging the `updated_after` Filter

All of the collection endpoints support an `updated_after` filter. As you'd guess, that's going to only return records that have been updated after the timestamp you pass to us.

### Example/Scenario/Not a Fable

How does that help with performance and caching? By only returning the records that you need to do something with.

Let's say you're building [a statistics site](https://www.wkstats.com/). You need to know about all the subjects plus get all of a user's assignments, review statistics, reviews, resets, and level progressions to figure out how they've done in the past and do some guesswork on how they might do in the future.

Focusing in on the assignments, let's say you decide to re-calculate a user's progress every time they log to use your site. Without the `updated_after` filter, you'd have to grab _all_ their assignments, since there'd be no way to tell which ones had changed until after you retrieved them all. For high level users, that could be 18 sequential requests! Once you've made them sit through _that_ progress bar, you'd need to parse all the results and compare to them what you've stored locally.

With the `updated_after` filter, though, you can ask for only the records that have changed since the last time that user logged in, getting a smaller, faster response full of records you know you have to update or add internally. Even high activity users are only going to touch a small portion of their assignments at a time. We can generate that list of records far more rapidly, it'll be a smaller payload, and you probably won't need to page through results to get everything that you need.


