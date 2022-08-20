# EMessage API Documentation

### EMessage Base URL 
`https://emessage.co.tz/api`

### Sending Message

Make a POST request to `/send-message` containing your API key, Vendor name, Message Receivers and Message. 

Example
```JSON 
  {
    "apiKey": "76f2d6b6414fb924a3a42f344760b6",
    "vendor": "EMESSAGE", 
    "message": "Hello World",
    "receivers": [ "+255752628215", "+255657658515"]
  }
```

### Retrieve Vendor(s) Information 

Make a GET request to `vendor-info?apiKey=76f2d6b6414fb924a3a42f344760b6`
