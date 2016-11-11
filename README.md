#LIRI - Language Interpretation and Recognition Interface

## Introduction
LIRI is like SIRI (from iOS).  It is a command line node app that takes in parameters and gives you back data.

## Setup
#### 0. Clone the repo

#### 1. Install the following npm packages

* [twitter](https://www.npmjs.com/package/twitter)
* [spotify](https://www.npmjs.com/package/spotify)
* [request](https://www.npmjs.com/package/request)
	* The request npm package will be used to hit the OMDB API
		* [OMDB API](http://www.omdbapi.com)


#### 2. Create a file named keys.js and store it somewhere safe

* Inside keys.js insert the following code:

``` JavaScript

exports.twitterKeys = {
  consumer_key: '<input here>',
  consumer_secret: '<input here>',
  access_token_key: '<input here>',
  access_token_secret: '<input here>',
}

```

#### 3. Get your Twitter API credentials by following these steps (you must have a Twitter account and be logged in)

* Step One: go to https://apps.twitter.com/app/new and fill out and submit the form
* Step Two: go to Keys and Access Tokens to get your consumer key and consumer secret
* Step Three: then click the button below on that page to create an access token and access token secret

After you get those credentials fill in the <input here> portions in the keys.js file (make sure the values are enclosed in quotes).

#### 4. Inside liri.js, enter your Twitter username in the params object to retrieve your last 20 tweets

``` JavaScript

var params = {
    screen_name: 'yourTwitterUsername'
} && {
    count: 20
};

```

## Run the application
* To install globally:
```
npm install -g
```
The syntax to run the program is:
```
liri <function> <parameter>
```

Available functions:
* mytweets

* spotify

* omdb

* random

Running the following commands in your terminal will do the following:

```
liri mytweets
```
* will log your last 20 tweets and when they were created

```
liri spotify <song name>
```

* log the following information about the song:

	* artist(s)
	* song name
	* preview link of the song from spotify
	* album that the song is a part of
	* song name

* if no song is provided then the program will output information for the song 'Computer Love' by Zapp by default

```
liri omdb <movie name>
```

* this would log the following information about the movie:

	* Title
	* Year
	* IMDB Rating
	* Country
	* Language
	* Plot
	* Actors
	* Rotten Tomatoes Rating
	* Rotten Tomatoes URL

* if no movie is provided then the program will output information for the movie 'WarGames' by default

```
node liri do-what-it-says
```

* The program will take the text inside of random.txt and use it to call the first command with the second part as it's parameter

* Currently in random.txt, the following text is there:

```
spotify, "Peter Piper"
```

* This would call the spotifyThis function and pass in "Peter Piper" as the song.

* This should work for any function and parameter you use.

* Terminal commands and output are logged in terminal.log.

## Debugging This Program (optional)
You can install iron-node globally to use to debug things.

```
npm install iron-node -g;
```

To use iron-node:
	* put a debugger; on the line where you want to stop the program
	* run the program like this from the console:

```
iron-node liri.js
```

# Copyright
Ryan Sy (C) 2016. All Rights Reserved.
