# Additional routes

## File upload

```shell
curl -X POST \
  https://cransten.herokuapp.com/api/users/1/files \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
 "category": "avatar",
 "file": "data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg==",
 "name": "slika.jpg"
}'
```

> The above route returns JSON structured like this:

```json
https://s3.eu-central-1.amazonaws.com/cransten-images/files/avatar/ID/image.jpg
```

This endpoint generate file link and returns it, for a user with ID.

### HTTP Request

`POST https://cransten.herokuapp.com/api/users/ID/files`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  |  id of user

### BODY Parameters

Parameter | Description
--------- | -----------
category  |  id of users
file  |  base64 data of image
name  |  name of file with extension

<aside class="notice">
If name is not provided it saves a file without extension!
</aside>

## Create Status

```shell
curl -X POST \
  https://cransten.herokuapp.com/create/status \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
	"status": "awaiting"
}'
```

> The above route returns JSON structured like this:

```json
{
    "status": "verified",
    "updated_at": "2018-06-19 22:12:58",
    "created_at": "2018-06-19 22:12:58",
    "id": 2
}
```

This endpoint creates a status in database.

### HTTP Request

`POST https://cransten.herokuapp.com/create/status`

### URL Parameters

Parameter | Description
--------- | -----------
-		  |  -

## Send Email to Admin

```shell
curl -X GET \
  https://cransten.herokuapp.comapi/users/ID/mails \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
```

> The above route returns JSON structured like this:

```json
{
    "message": "successful"
}
```

This endpoint sends an email to an admin, that user wit ID is ready for review.

### HTTP Request

`GET https://cransten.herokuapp.comapi/users/ID/mails`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  |  id of user