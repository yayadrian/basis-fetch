Quick module to get one days metrics from the Basis Peak private API.
Could break at any time.
Sorry there are no tests or support for other data types.

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