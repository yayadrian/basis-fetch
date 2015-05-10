#Basis-fetch

Quick module to get one days metrics from the Basis Peak private API.
Using the Basis private API so it could break at any time.
Tests and support for other data types coming soon.

## Install
```sh
$ npm install basis-fetch
```
## Access Token
Username and Password thay ou use on https://app.mybasis.com/
```javascript
  basis.requestUser(username, password, "2015-05-04");
  // returns error, access token
 ``` 
 
 ## Get Metrics for a day
 Date Format: YYYY-MM-DD
 ```javascript
	basis.getMetrics(accessToken, "2015-05-03", "details", callback)
	// returns error, array of data
```

## Get Latest Data
Finds the most recent complete data.
```javascript
	basis.getLatest(data, function(metric) {
		console.log("time: ", moment.unix(metric.date).format("dddd, MMMM Do YYYY, h:mm:ss a"));
		console.log("temp (c): ", convertTemp(metric.skinTemp));
		console.log("latest metric:", metric);
	}

 ```