# Gear_API_Doc

- **1. screen: Login, forgot-password, contct_us**
- **2. screen: jobList**
- **3. screen(filter):**
- **4. screen: qr(scanning), qr(api), jobDetail({id}), onHold(failed/{id}), delivered(deliver/{id})**
- **5. screen(recipient_type): recipient(api)**
- **6. scrren(deliver): deliver(Api)**
- **7. screen(delivered): can use jobDetail(api) here aswell (maybe)**

## API Documentation:

- **Login: ("/auth/login")**

Request:
```json
{
  "email": "email@email.com",
  "password": "the_password",
  "remember_me": true,
  "device_token": "8dhdjwnd9jn2kd9ejn",
  "firebase_key": "jdidunneke83733en"
}
```

Response:
```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJh...",
  "data": { ...  },
  "token_type": "Bearer",
  "expires_at": "2025-09-10 10:22:15"
}
```

Response:
```json
{
  "message": "Unauthorized"
}
```


---

- **Forgot-password: ("/auth/forget-password")**

Request:
```json
{
  "email": "user@example.com"
}
```

Response:
```json
{
  "api_status": 200,
  "message": "Please enter the OTP which is send to your registered email Id and reset your new  password",
  "error": false,
  "data": true,
  "otp": 123456,
  "otp_token": 98765432
}
```

Error:
```json
{
  "api_status": 401,
  "message": "Email Id is not registered.",
  "error": true,
  "data": "user@example.com"
}
```

---

- **Job List: ("/auth/jobList")**

**Bearer-token-required**

Response:

```json
{
  "error": false,
  "data": {
    "todo": [...],
    "delivered": [...],
    "onHold": [...]
  },
  "api_status": 200,
  "message": "Successful"
}

```

 ```json
{
	"error": false,
	"data": {
		"todo": {
			"current_page": 1,
			"data": [
				{
					"id": 688,
					"vehicle_id": null,
					"user_id": 119,
					"delivery_date": "2025-10-10",
					"address": "The Demo Address 3",
					"company": "The Demo Company",
					"contact_name": "Demo Contact Name",
					"last_name": "Demo Last Name",
					"contact_phone": 1111111111,
					"email": "demo@demo.com",
					"sender_phone": 1111111111,
					"delivery_time": "2:00PM",
					"eta": "5 hr",
					"instructions": "",
					"billing_address": "Demo Billing Address",
					"owner_name": "Demo Owener Name",
					"payment_mode": "Online",
					"payment_amt": "2300",
					"remarks": "The Demo Remark",
					"recipient_type": "Receptionist",
					"recipient_name": "Demo Recipient Name",
					"job_status": "In Progress",
					"created_at": "2025-09-04 04:23:36",
					"updated_at": "2025-09-04 04:25:12",
					"gearId": "GT827386",
					"signature": "",
					"image": "",
					"zipcode": 1,
					"job_type": "Delivery",
					"added_by": 1,
					"deleted_at": null
				}
			],
			"first_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"from": 1,
			"last_page": 1,
			"last_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"links": [
				{
					"url": null,
					"label": "&laquo; Previous",
					"active": false
				},
				{
					"url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
					"label": "1",
					"active": true
				},
				{
					"url": null,
					"label": "Next &raquo;",
					"active": false
				}
			],
			"next_page_url": null,
			"path": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList",
			"per_page": 10,
			"prev_page_url": null,
			"to": 1,
			"total": 1
		},
		"delivered": {
			"current_page": 1,
			"data": [
				{
					"id": 686,
					"vehicle_id": null,
					"user_id": 119,
					"delivery_date": "2025-10-10",
					"address": "The Demo Address",
					"company": "The Demo Company",
					"contact_name": "Demo Contact Name",
					"last_name": "Demo Last Name",
					"contact_phone": 1111111111,
					"email": "demo@demo.com",
					"sender_phone": 1111111111,
					"delivery_time": "2:00PM",
					"eta": "5 hr",
					"instructions": "",
					"billing_address": "Demo Billing Address",
					"owner_name": "Demo Owener Name",
					"payment_mode": "Online",
					"payment_amt": "2300",
					"remarks": "The Demo Remark Given",
					"recipient_type": "Receptionist",
					"recipient_name": "Demo Recipient Name Given",
					"job_status": "Delivered",
					"created_at": "2025-09-04 04:18:30",
					"updated_at": "2025-09-04 04:59:26",
					"gearId": "GT827384",
					"signature": "",
					"image": "https:\/\/gearapp.allproject.online\/public\/uploads\/deliveryImage\/175696196635.png",
					"zipcode": 1,
					"job_type": "Delivery",
					"added_by": 1,
					"deleted_at": null
				}
			],
			"first_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"from": 1,
			"last_page": 1,
			"last_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"links": [
				{
					"url": null,
					"label": "&laquo; Previous",
					"active": false
				},
				{
					"url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
					"label": "1",
					"active": true
				},
				{
					"url": null,
					"label": "Next &raquo;",
					"active": false
				}
			],
			"next_page_url": null,
			"path": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList",
			"per_page": 10,
			"prev_page_url": null,
			"to": 1,
			"total": 1
		},
		"onHold": {
			"current_page": 1,
			"data": [
				{
					"id": 687,
					"vehicle_id": null,
					"user_id": 119,
					"delivery_date": "2025-10-10",
					"address": "The Demo Address 2",
					"company": "The Demo Company",
					"contact_name": "Demo Contact Name",
					"last_name": "Demo Last Name",
					"contact_phone": 1111111111,
					"email": "demo@demo.com",
					"sender_phone": 1111111111,
					"delivery_time": "2:00PM",
					"eta": "5 hr",
					"instructions": "",
					"billing_address": "Demo Billing Address",
					"owner_name": "Demo Owener Name",
					"payment_mode": "Online",
					"payment_amt": "2300",
					"remarks": "The Demo Remark",
					"recipient_type": "Receptionist",
					"recipient_name": "Demo Recipient Name",
					"job_status": "Hold",
					"created_at": "2025-09-04 04:23:36",
					"updated_at": "2025-09-04 05:12:22",
					"gearId": "GT827385",
					"signature": "",
					"image": "",
					"zipcode": 1,
					"job_type": "Delivery",
					"added_by": 1,
					"deleted_at": null
				}
			],
			"first_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"from": 1,
			"last_page": 1,
			"last_page_url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
			"links": [
				{
					"url": null,
					"label": "&laquo; Previous",
					"active": false
				},
				{
					"url": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList?page=1",
					"label": "1",
					"active": true
				},
				{
					"url": null,
					"label": "Next &raquo;",
					"active": false
				}
			],
			"next_page_url": null,
			"path": "https:\/\/gearapp.allproject.online\/api\/auth\/jobList",
			"per_page": 10,
			"prev_page_url": null,
			"to": 1,
			"total": 1
		}
	},
	"api_status": 200,
	"message": "Successful"
}
```
---

- **GET: Job Detail: ("/auth/jobDetail/{id}") id=job_id**

**Bearer-token-required**

Response:
```json
{
	"message": "Success",
	"error": false,
	"api_status": 200,
	"data": {
		"id": 686,
		"vehicle_id": null,
		"user_id": 119,
		"delivery_date": "2025-10-10",
		"address": "The Demo Address",
		"company": "The Demo Company",
		"contact_name": "Demo Contact Name",
		"last_name": "Demo Last Name",
		"contact_phone": 1111111111,
		"email": "demo@demo.com",
		"sender_phone": 1111111111,
		"delivery_time": "2:00PM",
		"eta": "5 hr",
		"instructions": "",
		"billing_address": "Demo Billing Address",
		"owner_name": "Demo Owener Name",
		"payment_mode": "Online",
		"payment_amt": "2300",
		"remarks": "The Demo Remark Given",
		"recipient_type": "Receptionist",
		"recipient_name": "Demo Recipient Name Given",
		"job_status": "Delivered",
		"created_at": "2025-09-04T04:18:30.000000Z",
		"updated_at": "2025-09-04T04:59:26.000000Z",
		"gearId": "GT827384",
		"signature": "",
		"image": "https:\/\/gearapp.allproject.online\/public\/uploads\/deliveryImage\/175696196635.png",
		"zipcode": 1,
		"job_type": "Delivery",
		"added_by": 1,
		"deleted_at": null,
		"createdAt": "2025-09-04",
		"updatedAt": "2025-09-04"
	}
}
```

Error:
```json
{
  "message": "Failed",
  "error": true,
  "api_status": 400
}
```
---

- **GET: QR: ("/auth/qr/{id}") id=gear_id**

**Bearer-token-required**

Response:
```json
{
	"message": "Success",
	"error": false,
	"api_status": 200,
	"data": [
		{
			"no": 687,
			"id": 687,
			"contact_name": "Demo Contact Name",
			"address": "The Demo Address 2",
			"contact_phone": 1111111111
		}
	]
}
```
Error: Data will come empty

---
- **POST: Deliver: ("/auth/deliver/{id}") id=job_id**

**Bearer-token-required**

Request: (multipart-formdata)
| Field          | Type    | Description                             |
|----------------|---------|-------------------------------------|
| recipient_type | string  | The type of recipient (e.g., customer) |
| recipient_name | string  | The name of the recipient             |
| remarks        | string  | Remarks about the delivery            |
| image[]        | file[]  | Array of image files (multipart upload) |
| signature      | file    | Signature file (single file upload)  |

Response:
```json
{
  "message": "Delivered Successfully",
  "error": false,
  "api_status": 200
}
```

Error:
```json
{
  "message": "Failed",
  "error": true,
  "api_status": 400
}
```

---

- **GET: Failed(On-hold): ("/auth/failed/{id}") id=job_id**

**Bearer-token-required**

Response:
```json
{
	"message": "Success",
	"error": false,
	"api_status": 200,
	"job_status_msg": "Job status updated successfully"
}
```

Error:
```json
{
	"message": "Failed",
	"error": true,
	"api_status": 400
}
```

---

- **GET: Recipient: ("/auth/recipient")**

**Bearer-token-required**

Response:
```json
{
	"message": "Successfull",
	"error": false,
	"api_status": 200,
	"data": [
		{
			"id": 1,
			"recipient": "Buyer",
			"recipient_type": "Recipient"
		},
		{
			"id": 2,
			"recipient": "Receptionist",
			"recipient_type": "Recipient"
		},
		{
			"id": 3,
			"recipient": "Family Member",
			"recipient_type": "Recipient"
		},
		{
			"id": 4,
			"recipient": "Neighbour",
			"recipient_type": "Recipient"
		},
		{
			"id": 5,
			"recipient": "Friend",
			"recipient_type": "Recipient"
		},
		{
			"id": 6,
			"recipient": "Others",
			"recipient_type": "Recipient"
		},
		{
			"id": 7,
			"recipient": "Riser",
			"recipient_type": "No One"
		},
		{
			"id": 8,
			"recipient": "Shoe Rack",
			"recipient_type": "No One"
		},
		{
			"id": 9,
			"recipient": "Doorstep",
			"recipient_type": "No One"
		},
		{
			"id": 10,
			"recipient": "Parcel Drop Box",
			"recipient_type": "No One"
		},
		{
			"id": 11,
			"recipient": "Other Place",
			"recipient_type": "No One"
		}
	]
}
```
---

- **GET: Remarks: ("/auth/remarks")**

**Bearer-token-required**

Response:
```json
{
	"message": "Successfull",
	"error": false,
	"api_status": 200,
	"data": [
		{
			"id": 1,
			"remarks": "No phone call during office hour"
		},
		{
			"id": 2,
			"remarks": "Call to confirm before delivery"
		},
		{
			"id": 3,
			"remarks": "Babies and children at home"
		},
		{
			"id": 4,
			"remarks": "Beware of the dog"
		},
		{
			"id": 5,
			"remarks": "Contactless Delivery; authorised to leave the parcel(s) at the doorstep and communicate via text"
		},
		{
			"id": 6,
			"remarks": "No door knocking"
		},
		{
			"id": 7,
			"remarks": "No door bell ringing"
		},
		{
			"id": 8,
			"remarks": "Male driver to deliver"
		},
		{
			"id": 9,
			"remarks": "Female driver to deliver"
		},
		{
			"id": 10,
			"remarks": "Other,please type"
		}
	]
}
```
---
- **GET: Summary: ("/auth/summarry")** *Not a typo the spelling is really "summarry"

**Bearer-token-required**

Response:
```json
{
	"error": false,
	"data": {
		"all": 3,
		"inprogress": 1,
		"completed": 1,
		"failed": 1
	},
	"api_status": 200,
	"message": "Successful"
}

```

