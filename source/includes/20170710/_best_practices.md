# Best Practices

We're always working to make the API as performant as possible, but there are a few things you can do to optimize your use of the data we deliver and speed things up when you need to make new requests: [cache data locally](#caching) whenever possible, [make conditional requests](#conditional-requests) to minimize network load, and [make use of the `updated_after` filter](#leveraging-the-code-updated_after-code-filter) on a lot of the endpoints.

When you're building applications or services that other people will use, there's also some work to be done to [respect the access to content granted by a subscription](#respecting-subscription-restrictions) to WaniKani (per our terms and generally being a good citizen).
