# Bike Trail & Jump Counter

### [Check out my YouTube video on this code](https://youtu.be/DNJfUPfSZpY)

References: [Using Python to Explore Strava Activity Data by Matt Ambrogi](https://towardsdatascience.com/using-the-strava-api-and-pandas-to-explore-your-activity-data-d94901d9bfde)

This jupyter notebook uses the Strava API to collect the trails you have riden based on all of your activities.  With this trail data you can then fill in the csv file *trail_jumps.csv* to capture how many jumps are on a given trail.  This file and your trail data are then merged to provide the number of jumps you performed per day.

## Steps to complete before launching jupyter notebook

1. Set up Strava account and log your activities  
2. Create an API application with Strava [here](https://www.strava.com/settings/api).  (Note: For 'Website' put in any domain, and for 'Authorization Callback Domain' put 'localhost')
3. Get authorization code (i.e. grant permission for python file to access your Strava data)  
a. Put your 'Client ID' in the following link (your_client_id), to then be put into your browser bar, press ENTER  
`https://www.strava.com/oauth/authorize?client_id=your_client_id&redirect_uri=http://localhost&response_type=code&scope=activity:read_all`  
b.  Authorize the API to connect to Strava   
c.  Get authorization code (your_authorization_code) from returned url in browser bar:  
`http://localhost/?state=&code=your_authorization_code&scope=read,activity:read_all`  
4. Get access and refresh tokens by using a POST request.  (Note: You can use python for this, but I found Postman was easier)  
a.  Create a [postman account](https://www.postman.com/)    
b.  Create a POST request with your 'Client ID', 'Client Secret', and 'Authorization Code' using the following URL:  
`https://www.strava.com/oauth/token?client_id=your_client_id&client_secret=your_client_secret&code=your_authorization_code&grant_type=authorization_code` 
5. Obtain 'Refresh Token' and 'Access Token' to be used (along with 'Client ID') in python file to pull your data   
