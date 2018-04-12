## Caching

Most of the data on WaniKani doesn't change that often, so long-lived local caches or even more permanent local stores that are periodically updated can eliminate a lot of time-consuming requests.

* Cache subjects as aggressively as possible. Very infrequent updates.
* Reviews and resets are never changed once recorded.
* Assignments, review statistics, and study materials have moderate levels of updates. When a user levels up or passes a a subject, there might be a small flurry of activity with new assignments being created and existing records being updated. As an assignment gets further and further along in the SRS stages, those updates will become less and less frequent.
* The summary report changes every hour. Caching the results of this request might help with offline activity, but the data changes, well, every hour.
* The user endpoint isn't updated a ton, but when it does, it's going to be pretty important to capture.

Caching is always tricky business. When do you expire it? How do you refresh it? Who's in charge of it?

We've done a couple things to try and help with a couple of the problems around caching. The first is to support conditional requests, making any checks to see if a particular record has been updated as fast as possible. The second is to give you some tools to get things that have changed since the last time you checked, letting you easily refresh your local data caches and stores without having to parse _all_ the records.
