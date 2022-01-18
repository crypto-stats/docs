# HTTP

The HTTP library allows simple HTTP requests to be sent in an adapter.

## `sdk.http.get(url: string, options?: any): Promise<any>`

Sends an HTTP GET request. If the response is JSON-encoded, it will be automatically parsed
into an object.

The optional "options" field supports any values used by the [Javascript fetch function](https://developer.mozilla.org/en-US/docs/Web/API/fetch#parameters).

## `sdk.http.post(url: string, body: any, options?: any): Promise<any>`

Sends an HTTP POST request. If the body is included, it will be JSON-encoded.

The optional "options" field supports any values used by the [Javascript fetch function](https://developer.mozilla.org/en-US/docs/Web/API/fetch#parameters).

