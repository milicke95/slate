---
title: Cransten API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - users
  - updates
  - additional_routes
  - errors

search: false
---

# Introduction

Welcome to the Cransten API! This is Cransten API endpoints, which can get information on users.

We have language bindings in cURL! You can view code examples in the dark area to the right.

This API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl -X POST \
  https://cransten.herokuapp.com/oauth/token \
  -H 'Accept: application/json' \
  -H 'Cache-Control: no-cache' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' \
  -F grant_type=password \
  -F client_id=ID \
  -F client_secret=CLIENT SECRET \
  -F username=example@email.com \
  -F password=pass \
  -F scope=
```

> Make sure to replace `CLIENT SECRET` with your client_secret and `ID` with your client_id.

Cransten uses API access tokens to allow access to the API.

Cransten API expects for the API access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer ACCESS TOKEN`

<aside class="notice">
You must replace <code>ACCESS TOKEN</code> with your personal API access token.
</aside>

