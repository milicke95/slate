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
ID		  |  The Id of user

### BODY Parameters

Parameter | Description
--------- | -----------
category  |  category of file
file  |  base64 data of image
name  |  name of file with extension

<aside class="notice">
If name is not provided it saves a file without extension!
</aside>

## Reset User Password

```shell
curl -X POST \
  https://cransten.herokuapp.com/forgotten-password/ \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/json' \
```

> The above route returns JSON structured like this:

```json
{
    "message": "successful"
}
```

This endpoint resets user password and an email is sent to user with new generated password.

### HTTP Request

`POST https://cransten.herokuapp.com/forgotten-password`

### BODY Parameters

Parameter | Description
--------- | -----------
email		  |  email of user

### URL Parameters

Parameter | Description
--------- | -----------
-		  |  -