# Introduction

Welcome to "WaniKani: The API", subtitled "Version 2: The Separating"! You can use our API to access all the progress data for a user's account and a ton general reference data for the subjects within WaniKani.

This version is built around a [REST](#)ful structure, with consistent, resource-oriented URLs. We support that structure with standard HTTP features: [HTTP verbs](#) for all our endpoints to indicate different actions, [HTTP authentication headers](#), and [HTTP response codes](#) to indicate both success and various errors. We've also turned on cross-origin resource sharing to allow for secure client-side access. We also respond to all requests with JSON, making it easy to parse those responses into native objects in a variety of languages. These should open up the API to any client that supports these features and data structures.

We've got information on general usage, like authentication and error codes, in [Getting Started](#getting-started). We make a few suggestions on how to optimize your usage of the API in [Best Practices](#best-practices) and clarify a few obscure topics under [Additional Information](#additional-information). Finally, details for all of the available resources and endpoints are under [Resources](#).

Feel free to reach out [via email](mailto:hello@wanikani.com) or [through the community](https://community.wanikani.com/) if you have any questions, comments, or requests about the API.

<aside class="warning">
  <strong>Keep in mind this is an alpha! Expect breaking changes until the structure has been solidified. There may be more endpoints to come and the structure of API results can be changed dramatically before the beta release.</strong>
</aside>


<!-- ## Roadmap

The following are planned to be implemented before exiting beta:

* Soft deletion field.
* API terms and conditions.
* Inclusion of asset content:
  * Vocabulary audio
  * Sentences
  * Radical SVG and PNG
* JSON authentication endpoint for better extraction of API key.
* Move API v2 to subdomain api.wanikani.com/v2. -->
