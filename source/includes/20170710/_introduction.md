# Introduction

Welcome to <span title="Version 2: The Separating">"WaniKani: The API"</span>! You can use our API to access progress data for a user's account and a ton general reference data for the subjects within WaniKani.

This version is built around a [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer)ful structure, with consistent, resource-oriented URLs. We support that structure with standard HTTP features: [HTTP verbs](#) for all our endpoints to indicate different actions, [HTTP authentication headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods), and [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) to indicate both success and various errors. We've turned on cross-origin resource sharing to allow for secure client-side access. We respond to all requests with JSON, making it easy to parse those responses into native objects in a variety of languages. These should open up the API to any client that supports these features and data structures.

We've got information on general usage, like authentication and error codes, in [Getting Started](#getting-started). We make a few suggestions on how to optimize your usage of the API in [Best Practices](#best-practices) and clarify a few obscure topics under [Additional Information](#additional-information). Finally, details for all of the available resources and endpoints are under [Resources](#resources).

Feel free to reach out [via email](mailto:hello@wanikani.com) or [through the community](https://community.wanikani.com/) if you have any questions, comments, or requests about the API.
