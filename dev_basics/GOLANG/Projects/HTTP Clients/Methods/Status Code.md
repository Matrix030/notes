The `Status Code` of an HTTP _response_ tells the client whether or not the server was able to fulfill the request. Status codes are 3-digit numbers that are grouped into categories:

- `100-199`: Informational responses. These are very rare.
- `200-299`: Successful responses. Hopefully, most responses are 200's!
- `300-399`: Redirection messages. These are typically invisible because the browser or HTTP client will automatically do the redirect.
- `400-499`: Client errors. You'll see these often, especially when trying to debug a client application
- `500-599`: Server errors. You'll see these sometimes, usually only if there is a bug on the server.

Here are some of the most common status codes, but there is also a [full list here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) if you're interested.

- `200` - OK. This is by far the most common code, it just means that everything worked as expected.
- `201` - Created. This means that a resource was created successfully. Typically in response to a `POST` request.
- `301` - Moved permanently. This means the resource was moved to a new place, and the response will include where that new place is. Websites often use `301` redirects when they change their domain name, for example.
- `400` - Bad request. A general error indicating the client made a mistake in their request.
- `401` - Unauthorized. This means the client doesn't have the correct permissions. Maybe they didn't include a required authorization header, for example.
- `404` - Not found. You'll see this on websites quite often. It just means the resource doesn't exist.
- `500` - Internal server error. This means something went wrong on the server, likely a bug on their end.

## Don't Memorize

It's good to know the basics by heart, like "2XX is good", "4XX is a client error", and "5XX is a server error". But don't memorize all the status codes... they're easy to [look up](https://http.cat/).

![](https://storage.googleapis.com/qvault-webapp-dynamic-assets/course_assets/FJl2z9O-549x454.jpg)