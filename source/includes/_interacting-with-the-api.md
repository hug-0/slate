# Interacting with the API

## Making Requests

## Status Codes

The following status codes 

| Status Code | Description |
|-------------|-------------|
| `200` | This is a status code message description |
| ... | ... |

## Response Formats

## Scopes

## Pagination

## Errors

<aside class="notice">This error section is stored in a separate file in `includes/_errors.md`. Slate allows you to optionally separate out your docs into many files...just save them to the `includes` folder and add them to the top of your `index.md`'s frontmatter. Files are included in the order listed.</aside>

Error | Code | Description
----- | -----| -----------
`bad_request`| 400  | Bad Request -- Your request sucks
`f` | 401 | Unauthorized -- Your API key is wrong
`f` | 403 | Forbidden -- The kitten requested is hidden for administrators only
`f` | 404 | Not Found -- The specified kitten could not be found
`f` | 405 | Method Not Allowed -- You tried to access a kitten with an invalid method
`f` | 406 | Not Acceptable -- You requested a format that isn't json
`f` | 410 | Gone -- The kitten requested has been removed from our servers
`f` | 418 | I'm a teapot
`f` | 429 | Too Many Requests -- You're requesting too many kittens! Slow down!
`f` | 500 | Internal Server Error -- We had a problem with our server. Try again later.
`f` | 503 | Some text

## Request Rate Limiting

