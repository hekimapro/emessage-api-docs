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
