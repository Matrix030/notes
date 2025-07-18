Making a `POST` request with cURL is almost as simple as a GET request. Use the `-X POST` option to specify the request method and the `-d` option to pass data.

Here's how to make a POST request:

```sh
curl -X POST http://example.com/resource -d "param1=value1&param2=value2"
```

This command makes an HTTP `POST` request to `http://example.com/resource` with the data `param1=value1&param2=value2`. The server's response body is written to `stdout`.

If you need to send JSON data, use the `-H` option to set the `Content-Type` header and the `-d` option to pass the JSON data:

```sh
curl -X POST http://example.com/resource -H "Content-Type: application/json" -d '{"key1":"value1","key2":"value2"}'
```