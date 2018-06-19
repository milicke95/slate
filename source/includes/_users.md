# Users

## Get All Users

```shell
curl -X GET \
  https://cransten.herokuapp.com/api/users/ \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
  -H 'Content-Type: application/json' \
```

> The above route returns JSON structured like this:

```json
[
	{
		"id": 1,
		"first_name": "Example",
		"last_name": "Examplovic",
		"middle_name": "Examplivius",
		"email": "example@email.com",
		"image": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/avatar/1/example-3.jpg",
		"social_number": "3213-312-533",
		"proof_of_liability": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/licenses/2/user8proof.pdf",
		"proof_of_liability_link": "link",
		"date_of_birth": "25/05/2001",
		"hat_size": "L",
		"shirt_size": "L",
		"role": "user",
		"percentages": {
			"personal": 100,
			"experience": 100,
			"legal": 70,
			"bank": 100,
			"total_overview": 90
		},
		"created_at": "16/06/2018",
		"created_at_humans": "3 days ago",
		"updated_at": "17/06/2018",
		"updated_at_humans": "2 days ago",
		"flags": {
			"personal_info_flag": null,
			"additional_info_flag": null,
			"experience_flag": null,
			"bank_flag": null,
			"legal_flag": null,
			"personal_info_flag_msg": null,
			"additional_info_flag_msg": null,
			"experience_flag_msg": null,
			"bank_flag_msg": null,
			"legal_flag_msg": null
		},
		"notes": [],
		"addresses": [
			{
				"id": 1,
				"user_id": 1,
				"address": "A1",
				"city": "C1",
				"state": "S1",
				"zip": 1234,
				"primary": false,
				"created_at": "17/06/2018",
				"updated_at": "18/06/2018",
				"created_at_humans": "2 days ago",
				"updated_at_humans": "1 day ago"
			}
		],
		"cellPhones": [
			{
				"id": 1,
				"user_id": 1,
				"number": "555-888-7777",
				"provider": "Cricket",
				"primary": 0,
				"created_at": "17/06/2018",
				"updated_at": "17/06/2018",
				"created_at_humans": "2 days ago",
				"updated_at_humans": "2 days ago"
			}
		],
		"bankAccounts": [
			{
				"id": 2,
				"user_id": 1,
				"routing_number": "555588888",
				"account_number": "555",
				"bank_name": "New",
				"void_check_image": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/bank_info/1/voidcheck.jpeg",
				"primary": false,
				"created_at": "17/06/2018",
				"updated_at": "17/06/2018",
				"created_at_humans": "2 days ago",
				"updated_at_humans": "2 days ago"
			}
		],
		"jobs": [
			{
				"id": 2,
				"user_id": 1,
				"type": "Sub-contractors",
				"created_at": "17/06/2018",
				"updated_at": "17/06/2018",
				"skills": [
					"Pool maintenance and Repair",
					"Home Rehab",
					"Load and Unload Only Moving Services",
					"Kitchen & Appliances"
				],
				"licenses": [
					{
						"id": 2,
						"job_id": 2,
						"license": "Mrs.",
						"link": null,
						"category": "Electronic Equipment Assembler",
						"state": "American Samoa",
						"expiration_date": "19/06/2020",
						"created_at": "17/06/2018",
						"updated_at": "17/06/2018",
						"created_at_humans": "2 days ago",
						"updated_at_humans": "2 days ago"
					}
				],
				"licenses_archive": [
					{
						"id": 1,
						"job_id": 2,
						"license": "Ms.",
						"link": null,
						"category": "Electronic Equipment Assembler",
						"state": "American Samoa",
						"expiration_date": "19/06/2018",
						"created_at": "17/06/2018",
						"updated_at": "17/06/2018",
						"created_at_humans": "2 days ago",
						"updated_at_humans": "2 days ago"
					}
				],
				"created_at_humans": "2 days ago",
				"updated_at_humans": "2 days ago"
			}
		],
		"legals": {
			"id": 1,
			"user_id": 1,
			"background_doc": "ffff2.pdf",
			"name_confirmation_doc": "ffff2.pdf",
			"visual_confirmation_doc": "vaptest.pdf",
			"background_doc_link": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/background_doc/1/ffff2.pdf",
			"name_confirmation_doc_link": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/name_confirmation_doc/1/ffff2.pdf",
			"visual_confirmation_doc_link": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/visual_confirmation_doc/1/vaptest.pdf",
			"visual_appearance_verification_id": "Drivers Licence",
			"name_verification_id": "Passport",
			"created_at": "17/06/2018",
			"updated_at": "17/06/2018"
		},
		"bankDocuments": [
			{
				"id": 1,
				"user_id": 1,
				"link": "https://s3.eu-central-1.amazonaws.com/cransten-images/files/tax_document/2/ffff2.pdf",
				"name": "ffff2.pdf",
				"type": "I-9",
				"created_at": "17/06/2018",
				"updated_at": "17/06/2018",
				"created_at_humans": "2 days ago",
				"updated_at_humans": "2 days ago"
			}
		],
		"status": "awaiting",
		"contracts": {
			"contracts": [],
			"contracts_archive": []
		}
	}
]
```

This endpoint retrieves all users if role is super admin. 

If role is admin it retrieves all users who are not admins but without their bank account info.

If role is user then it retrieves only that user that sent request.

### HTTP Request

`GET https://cransten.herokuapp.com/api/users/`

### URL Parameters

Parameter | Default | Description
--------- | ------- | -----------
-		  | -		| -

<aside class="notice">
Response depends on the role of the user that is sendig request!
</aside>

## Get a Specific User

```shell
curl -X GET \
  https://cransten.herokuapp.com/api/users/ID \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
```

> The above route returns JSON structured like in the response [above](#get-all-users), only a single object.

This endpoint retrieves a specific user with ID.

### HTTP Request

`GET https://cransten.herokuapp.com/api/users/ID`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve

## Update a Specific User

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
  -d '{
  "first_name": "Example",
  "last_name": "Examplovic",
  "middle_name": "Examplivius",
  "proof_of_liability": "proof",
  "proof_of_liability_link": "link",
  "user_image": "link",
  "date_of_birth": "25/05/2001",
  "hat_size": "L",
  "shirt_size": "L",
  "social_number": "3213-312-533"
}'
```

> The above route returns JSON structured like in the response [above](#get-all-users).

This endpoint updates a specific user with ID.

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID`

### BODY Parameters

Parameter | Description
--------- | -----------
first_name | updates first name
last_name | updates last name
middle_name | update middle name
proof_of_liability | user proof of liability name
proof_of_liability_link | user proof of liabilty link
user_image | link to user image
date_of_birth | user date of birth
hat_size | user hat size
shirt_size | user shirt size
social_number | user social security number

## Get Current User

```shell
curl -X GET \
  https://cransten.herokuapp.com/api/user \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
```

> The above route returns JSON structured like the response [above](#get-all-users), only a single object.

This endpoint retreives a user that sent request.

### HTTP Request

`GET https://cransten.herokuapp.com/api/user`

### URL Parameters

Parameter | Description
--------- | -----------
- | -

## Update a Current User

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/user/ \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
  -d '{
  "first_name": "Example",
  "last_name": "Examplovic",
  "middle_name": "Examplivius",
  "proof_of_liability": "proof",
  "proof_of_liability_link": "link",
  "user_image": "link",
  "date_of_birth": "25/05/2001",
  "hat_size": "L",
  "shirt_size": "L",
  "social_number": "3213-312-533"
}'
```

> The above route returns JSON structured like in the response [above](#get-all-users), only a single object.

This endpoint updates a user that is sending the request.

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/user/`

### BODY Parameters

Parameter | Description
--------- | -----------
first_name | updates first name
last_name | updates last name
middle_name | update middle name
proof_of_liability | user proof of liability name
proof_of_liability_link | user proof of liabilty link
user_image | link to user image
date_of_birth | user date of birth
hat_size | user hat size
shirt_size | user shirt size
social_number | user social security number

## Delete a Specific User

```shell
curl -X DELETE \
  https://cransten.herokuapp.com/api/users/ID \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
```

> The above route returns JSON structured like this:

```json
{
  "message": "successful"
}
```

This endpoint deletes a specific user.

### HTTP Request

`DELETE https://cransten.herokuapp.com/api/users/ID`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to delete

<aside class="notice">
The message depends on wheter deletion was successful!
</aside>

## Register User

```shell
curl -X POST \
  https://cransten.herokuapp.com/register/ \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'\
  -H 'Content-Type: application/json' \
  -d '{
	"first_name": "Example",
	"last_name": "Examplovic",
	"middle_name": "Examplius",
	"email": "example@email.com",
	"password": "pass",
	"role": "user"
}'
```

> The above route returns JSON structured like the response [above](#get-all-users), only a single object:

This endpoint register a new user.

### HTTP Request

`POST https://cransten.herokuapp.com/register/`

### BODY Parameters

Parameter | Description
--------- | -----------
first_name | user first name
last_name | user last name
middle_name | user middle name
email | user email
password | user password
role | user role (default it is set to user)

## Filter Users

```shell
curl -X POST \
  https://cransten.herokuapp.com/api/users/filter \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token'
  -H 'Content-Type: application/json' \
  -d '{
	"type": "type2",
	"keyword": "Milan",
	"status": "awaiting",
	"filters":
	[
		"skill3"
	]
}'
```

> The above route returns JSON structured like the response [above](#get-all-users):

This endpoint retreives users with certain filters.

This route only retreives users with filters that are included in request.

All of the role constrains that exist in request [above](#get-all-users), exist here also.

### HTTP Request

`POST https://cransten.herokuapp.com/api/users/filter`

### BODY Parameters

Parameter | Description
--------- | -----------
type | user job type to be filtered
keyword | user last name or first name to be filtered
status | user status to be filtered
filters | user job skills to be filtered

<aside class="notice">
Some of body paramteres can be excluded from request.
</aside>
