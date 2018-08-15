# User Updates

## Change User Password

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/password \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
  "old_password": "pass",
  "new_password": "newpass"
}'
```
> The above route returns JSON structured like this:

```json
{
	"message" : "Password changed successfully!"
}
```

This endpoint changes password of users with ID, and an email is sent to with notification. 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/password`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
old_password | old user password
new_password | new user password

<aside class="notice">
The response depends on the success of the request! If an old password was incorrect or a new password is the same as an old one, a message containing an error is returned in the response.
</aside>

## Change User Email

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/email \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
	"old_email": "example@email.com",
	"new_email": "newmail@email.com"
}'
```

> The above route returns JSON structured like this:

```json
{
	"message" : "Email changed successfully!"
}
```

This endpoint changes email of users with ID, and an email is sent to new user email. 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/email`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
old_email | old user email
new_email | new user email

<aside class="notice">
The response depends on the success of the request! If an old email was incorrect or a new email is the same as an old one, a message containing an error is returned in the response.
</aside>

## Change User Role

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/role \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
	"role": "super admin"
}'
```

> The above route returns JSON structured like this:

```json
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
	"active": null,
	"eligible": null,
	"hr_department": null,
	"percentages": {
		"personal": 100,
		"experience": 100,
		"legal": 70,
		"bank": 100,
		"total_overview": 90
	},
	"overall_data_missing": {
		"personal": [],
		"address": [
			"Address"
		],
		"cellphone": [
			"Cellphone"
		],
		"additional": [],
		"experience": [
			"Job position"
		],
		"legal": [
			"Identity confirmation"
		],
		"background_check": [
			"Background information"
		],
		"name_identity": [
			"Name identity information"
		],
		"visual_identity": [
			"Visual identity information"
		],
		"work_agreement": [
			"Work agreement"
		],
		"bank": [
			"Bank information"
		],
		"tax_document": [
			"Tax documents"
		]
	},
	"hire_date": null,
	"hire_date_humans": null,
	"fire_resign_date": null,
	"fire_resign_date_humans": null,
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
	"status": "Registering",
	"contracts": {
		"contracts": [
		{
			"id": "1",
			"name": "contract name",
			"link": "link",
			"expiration_date": "11/21/2019",
			"created_at": "17/06/2018",
			"updated_at": "17/06/2018",
			"created_at_humans": "2 days ago",
			"updated_at_humans": "2 days ago"
		}
		],
		"contracts_archive": []
	}
}
```

This endpoint changes role of users with ID, and an email is sent to user with notification. 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/role`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
role | new role of user

<aside class="notice">
The response depends on the role of the user that has sent request! If an role is not super admin, response contains message about it.
</aside>

## Update User Flags

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/flag \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
  "personal_info_flag": "submitted",
  "additional_info_flag": "submitted",
  "experience_flag": "resubmission needed",
  "bank_flag": "verified",
  "legal_flag": "submitted",
  "address_flag": "submitted",
  "cellphone_flag" : "submitted",
  "background_check_flag" : "submitted",
  "work_agreement_flag" : "submitted",
  "tax_document_flag" : "submitted",
  "personal_info_flag_msg": "personal info flag message",
  "additional_info_flag_msg": "additional info flag message",
  "experience_flag_msg": "experience flag message",
  "bank_flag_msg": "bank flag message",
  "legal_flag_msg": "legal flag message",
  "address_flag_msg": "address flag message",
  "cellhpone_flag_msg": "cellphone flag message",
  "background_check_flag_msg": "backgorund check flag message",
  "work_agreement_flag_msg": "work agreement flag message",
  "tax_document_flag_msg": "tax document flag message"
}'
```
> The above route returns JSON structured like response [above](#change-user-role):

This endpoint changes flags of users with ID, thats suggest if users should update neccessary sections. 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/flag`

### BODY Parameters

Parameter | Description
--------- | -----------
personal_info_flag | personal section flag
additional_info_flag | additional section flag
experience_flag | experience section flag
bank_flag | bank section flag
legal_flag | legal section flag
address_flag | address section flag
cellphone_flag | cellphone section flag
background_check_flag | background check section flag
work_agreement_flag | work agreement section flag
tax_document_flag | tax document section flag
personal_info_flag_msg | personal section flag message
additional_info_flag_msg | additional section flag message
experience_flag_msg | experience section flag message
bank_flag_msg | bank section flag message
legal_flag_msg | legal section flag message
address_flag_msg | address section flag message
cellphone_flag_msg | cellphone section flag message
background_check_flag_msg | background check section flag message
work_agreement_flag_msg | work agreement section flag message
tax_document_flag_msg | tax document section flag message

### URL Parameters

Parameter | Description
--------- | -----------
ID | The id of user

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Status

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/status \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "status": "Verified",
}'
```

This endpoint update user status with ID, and response is like [above](#change-user-role). 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/status`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | The id of user

### BODY Parameters

Parameter | Description
--------- | -----------
status	| new user status

<aside class="notice">
Response depends of user role, only admins and super admins can change user roles.
</aside>

## Submit user registration

```shell
curl -X GET \
  https://cransten.herokuapp.com/api/users/ID/submit \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "status": "Verified",
}'
```

This endpoint submit user registration by seting all user flags with ID to "submitted" and status to "Needs verification". Response is like [above](#change-user-role). 

### HTTP Request

`GET https://cransten.herokuapp.com/api/users/ID/submit`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | The id of user

## Update User management info

```shell
curl -X POST \
  https://cransten.herokuapp.com/api/users/ID/manage \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "active": "true",
	"eligible": "false",
	"hr_department": "true",
	"fire_resign_date": "18/06/2018",
	"hire_date": "18/06/2018"
}'
```

This endpoint submit user registration by seting all user flags with ID to "submitted" and status to "Needs verification". Response is like [above](#change-user-role). 

### HTTP Request

`POST https://cransten.herokuapp.com/api/users/ID/manage`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | The id of user

### URL Parameters

Parameter | Description
--------- | -----------
active		  | true if user is active
eligible	| true if user eligible for rehire
hr_department		| true if user works in HR department
fire_resign_date	| fire or resign date
hire_date		| hire date

## Update User Legal

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/legals \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "background_doc": "b",
    "visual_confirmation_doc": "vc",
    "name_confirmation_doc": "nc",
    "background_doc_link": "bl",
    "visual_confirmation_doc_link": "vl",
    "name_confirmation_doc_link": "nl",
    "visual_appearance_verification_id": "Passport",
    "name_verification_id": "Id"
}'
```

This endpoint update legal of users with ID, and response is like [above](#change-user-role). 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/legals`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | The id of user

### BODY Parameters

Parameter | Description
--------- | -----------
background_doc | backgorund document name
visual_confirmation_doc | visual confirmation document name
name_confirmation_doc | name confirmation document name
background_doc_link | backgorund document link
visual_confirmation_doc_link | visual confirmation document link
name_confirmation_doc_link | name confirmation document link
visual_appearance_verification_id | visual verification option selected
name_verification_id | name verification option selected

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Address

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/addresses \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "address": "779 Marquardt Camp\nStromanside, FL 46645-5023",
    "city": "Corkeryside",
    "state": "United States",
    "zip": "23410",
    "primary": "1"
}'
```

This endpoint update address of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/address`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
address | address
city | city
state | state
zip | zip code
primary | is this primary address

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Cellphone

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/cellphones \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "number": "779",
    "provider": "Corkeryside",
    "primary": "1"
}'
```

This endpoint update cellphone of users with ID, and response is like [above](#change-user-role). 

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/cellphones`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
number | cellphone number
provider | cellphone provider
primary | is this primary cellphone

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Bank Account

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/banks \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "routing_number": "779",
    "account_number": "41284198",
    "bank_name": "Zimbabwe",
    "primary": "1"
}'
```

This endpoint update bank info of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/banks`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
routing_number | bank routing number
account_number | bank account number
bank_name | bank name
primary | is this primary bank account

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Tax Document

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/bankdoucments \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
	"link": "O",
	"name": "I",
	"type": "W-4",
    "archived_on": "6/2/2015"
}'
```

This endpoint update tax document of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/bankdoucments`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
link | link to document
name | document name
type | document type
archived_on | date when the doucment was acrihved

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Job

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/jobs \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "type": "Tehnician",
    "licenses":[
    	{
        "license": "Ms.",
        "category": "Electronic Equipment Assembler",
        "state": "American Samoa",
        "link": "link",
        "expiration_date": "11/21/2020"
    }
    ],
    "skills":[
    		"Smart Home Installations",
    		"Everything from the handyman website"
    		]
}'
```

This endpoint update job of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/jobs`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
type | job type
licenses | array of license objects
license | license name
category | license category
state | state where license was issued
link | link to document
expiration_date | expiration date of license
skills | array skills user possess

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Working Agreement 

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/contracts \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "name": "newname",
    "link": "newurl",
    "expiration_date": "11/21/2016"
}'
```

This endpoint update working agreement of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/contracts`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
name | document name
link | link to document
expiration_date | expiration date of working agreement

<aside class="notice">
All of the parameters are optionals.
</aside>

## Update User Job License

```shell
curl -X PATCH \
  https://cransten.herokuapp.com/api/users/ID/jobs/JOBID/licenses \
  -H 'Accept: application/json' \
  -H 'Authorization: access_token' \
  -H 'Content-Type: application/json' \
  -d '{
    "license": "Ms.",
    "category": "Electronic Equipment Assembler",
    "state": "American Samoa",
    "link": "link",
    "expiration_date": "11/1/2019"
}'
```

This endpoint update license of JOBID of users with ID, and response is like [above](#change-user-role).

### HTTP Request

`PATCH https://cransten.herokuapp.com/api/users/ID/jobs/JOBID/licenses`

### URL Parameters

Parameter | Description
--------- | -----------
ID		  | id of user

### BODY Parameters

Parameter | Description
--------- | -----------
license | license name
category | license category
state | state where license was issued
link | link to document
expiration_date | expiration date of license

<aside class="notice">
All of the parameters are optionals.
</aside>