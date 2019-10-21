# Errors

The Snackify API uses the following error codes:

| Error Code | Meaning                                                                                                     |
| ---------- | ----------------------------------------------------------------------------------------------------------- |
| 400        | Bad Request -- Your request is invalid.                                                                     |
| 401        | Unauthorized -- Your Session Token is not set or invalid.                                                   |
| 403        | Forbidden -- The info requested is hidden for administrators only.                                          |
| 404        | Not Found -- The specified kitten could not be found.                                                       |
| 405        | Method Not Allowed -- You tried to access an endpoint with an invalid method (i.e. POST, GET, PUT, DELETE). |
| 406        | Not Acceptable -- You requested a format that isn't json.                                                   |
| 409        | Missing Info -- Your request is missing informaion.                                                         |
| 410        | Gone -- The info requested has been removed from our servers.                                               |
| 418        | I'm a teapot.                                                                                               |
| 429        | Too Many Requests -- You're requesting too much data! Slow down!                                            |
| 500        | Internal Server Error -- We had a problem with our server. Try again later.                                 |
| 503        | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.                   |
