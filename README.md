#Stamps.com node.js client

A client for stamps.com API.

Sign up with [stamps.com developer program](http://developer.stamps.com/developer/) to receive credentials to the API.

##Installation
	npm install stamps-api

##API

###Create client
Create client for work with Stamps api.

```javascript
var Stamps = require('node-stamps-api');
```

###Auth client
For use most api's you need auth with your Stamps account data

```javascript
Stamps.connect().then(() => {
    Stamps.auth(options).then(() => {
    	console.log(options);
    });
});
```

options - is a object with fields

```json
{
    id: 'your_integrations_stamps_id',
    username: 'you_stmaps_username',
    password: 'you_stmaps_password'
}
```

###Make request
For send requests to stamps use this api after connect and auth. 
Example get track number.

```javascript
Stamps.request('TrackShipment', {
    TrackingNumber: 'needed_track_Number'
}).then(function(trackingResponse) {
	console.log(trackingResponse);
});
```

#Attention!!!
Follow the order of the fields.

#Run test

Before run test set env variables you stamps auth data:

```bash
STAMPS_ID
STAMPS_USERNAME
STAMPS_PASSWORD
```

```bash
npm test
```