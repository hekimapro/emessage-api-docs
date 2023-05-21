# EMessage API Documentation

### EMessage Base URL 
`https://emessage.plab.tech/api`

### Sending Message

Make a POST request to `/send-message` containing your API key, Vendor name, Message Receivers and Message. 
NOTE: `scheduled` and `scheduledDate` keys are optional.

Sample JSON Request:
```JSON 
   {
   	"apiKey": "d67bb59c1657891bc356663d657867",
	"vendor": "EMESSAGE", 
	"message": "Hello World",
	"receivers": [ "+255752628215", "+255657658515"],
	"scheduled": true,
	"scheduledDate": "2022-08-21T08:06:42.334+00:00"
  }
```
Sample JSON Response (Direct Message): 
```json
   {
	"success": true,
	"message": "Message has been sent"
   }
```

Sample JSON Response (Scheduled Message):
```json
   {
	"success": true,
	"message": "Message has been scheduled"
   }
```

### Retrieve Vendor(s) Information 

Make a GET request to `vendor-info?apiKey=76f2d6b6414fb924a3a42f344760b6`

Sample JSON Response: 
```json
   {
	"success": true,
	"message": [
			{
			     "_id": "62f70020914f5612519ca6ae",
			     "name": "EMESSAGE",
			     "balance": 7696,
			     "status": "approved"
			},
			{
			     "_id": "62f707c1b12fc3df2ac876e9",
			     "name": "SMASAPP",
			     "balance": 4840,
			     "status": "disabled"
			},
			{
			     "_id": "62f707c6b12fc3df2ac876f0",
			     "name": "TAPROTEC",
			     "balance": 1800,
			     "status": "approved"
			}
		]
   }
```

### Sending One Time Password (OTP) 
Make a POST request to `/send-otp` containing your API key, Vendor name, and Receiver.

Sample JSON Request: 
```json
   {
      "vendor": "emessage",
      "receiver": "+255752628215",
      "apiKey": "7d74c6d624d8bb5703d7bff8c81b5c"
   }
```

Sample JSON Response: 
```json
   {
	   "success": true,
	   "message": "One time password (OTP) has been sent to +255752628215"
   }
```

### Verifying  One Time Password (OTP)

Make a GET request to `/verify-otp?otp=378155&phoneNumber=255752628215`

Sample JSON Response: 
```json
   {
      "success": true,
      "message": {
         "_id": "6325a5c7b22f3ee6f11d7bad",
         "otp": "378155",
         "phoneNumber": "+255752628215"
      }
   }
```

### Load all Vendor Messages

Make a GET request to `/messages?apiKey=7d74c6d624d8bb5703d7bff8c81b5c&vendor=emessage`

Sample JSON Response: 
```json
	{
		"success": true,
		"message": [
			{
				"message": "Your one time password (OTP) is: 378155.\nValid for 5 minutes.",
				"cost": 28,
				"date": "2022-09-17T10:47:35.039Z",
				"receivers": [
					"+255752628215"
				]
			},
			{
				"message": "Your one time password (OTP) is: 348961",
				"cost": 28,
				"date": "2022-09-17T10:34:56.832Z",
				"receivers": [
					"+255752628215"
				]
			}
		]
	}
```

### Request Vendor Name

Make a POST request to `/api/request` containing your apiKey and vendor name to request

Sample JSON request
```json
   {
      "apiKey": "2161cf091012062796961a9a70caf6",
      "vendorName": "EMESSAGE"
   }
```

Sample JSON response 
```json
   {
       "success": true,
       "message": "Your request has been sent"
   }
```

