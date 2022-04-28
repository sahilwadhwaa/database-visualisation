# database-visualisation
Using the Google Places API with a Database and visualizing data on Google Map.<br><br>
In this project, we are using the Google geocoding API
to clean up some user-entered geographic locations of
university names and then placing the data on a Google
Map.<br>
The first problem to solve is that the Google geocoding
API is rate limited to a fixed number of requests per day.
So if you have a lot of data you might need to stop and
restart the lookup process several times.  So we break
the problem into two phases. <br>
In the first phase we take our input data in the file
(where.data) and read it one line at a time, and retrieve the
geocoded response and store it in a database (geodata.sqlite).<br>
Before we use the geocoding API, we simply check to see if
we already have the data for that particular line of input.<br>

You can re-start the process at any time by removing the file
geodata.sqlite<br>

Run the geoload.py program. This program will read the input
lines in where.data and for each line check to see if it is already
in the database and if we don't have the data for the location,
call the geocoding API to retrieve the data and store it in
the database.<br>

In recent years, the Google Geocoding APIs changed dramatically.
They moved some functionality that we use from the Geocoding API
into the Places API.  Also all the Google Geo-related APIs require an
API key. To complete this project without a Google account,
without an API key, or from a country that blocks
access to Google, you can use a subset of that data which is
available at: <br>

http://py4e-data.dr-chuck.net/json <br>

To use this, simply leave the api_key set to False in 
geoload.py. <br>

This URL only has a subset of the data but it has no rate limit so
it is good for testing. <br>


