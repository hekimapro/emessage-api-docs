# EMessage API Documentation

### EMessage Base URL 
`https://emessage.co.tz/api`

### Sending Message

Make a POST request to `/send-message` containing your API key, Vendor name, Message Receivers and Message. 

Example
```JSON 
   {
    "apiKey": "d67bb59c1657891bc356663d657867",
    "vendor": "EMESSAGE", 
    "message": "Hello World",
    "receivers": [ "+255752628215", "+255657658515"],
    "scheduled": true, // OPTIONAL
    "scheduledDate": "2022-08-21T08:06:42.334+00:00" // OPTIONAL
  }
```

### Retrieve Vendor(s) Information 

Make a GET request to `vendor-info?apiKey=76f2d6b6414fb924a3a42f344760b6`

### Sending One Time Password (OTP) 
Make a POST request to `/send-otp` containing your API key, Vendor name, and Receiver.

Example: 
```json
   {
      "vendor": "emessage",
      "receiver": "+255752628215",
      "apiKey": "7d74c6d624d8bb5703d7bff8c81b5c"
   }
```

Sample Response: 
```json
   {
	   "success": true,
	   "message": "One time password (OTP) has been sent to +255752628215"
   }
```

### Verifying  One Time Password (OTP)

Make a GET request to `/verify-otp?otp=378155&phoneNumber=+255752628215`

Sample Response: 
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
