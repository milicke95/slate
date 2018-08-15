# Errors

<aside class="notice">
This are some of errors that might happen in any request. In the table below you can see error codes and their meaning, giving you a hint what your next action should be.
</aside>

The Cransten API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API access token is wrong.
403 | Forbidden -- The user requested is hidden for administrators only.
404 | Not Found -- The specified user could not be found.
405 | Method Not Allowed -- You tried to access a user with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The user requested has been removed from our servers.
429 | Too Many Requests -- You're requesting too many users!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
