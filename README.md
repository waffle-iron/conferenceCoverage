##########################################
#           conferenceCoverage           #
##########################################


Help to get pass the OAuth with twitter

Log to your account on twitter.com (or create a new one).
Go to : https://dev.twitter.com/apps
Create a new app to get a consumerKey and a consumerSecret

The following lines are meant to be used in a R console

<!--:R-->
library(twitteR)

cred <- OAuthFactory$new(consumerKey="YOURCONSUMERKEY",
	consumerSecret="YOURCONSUMERSECRET",
	requestURL="https://api.twitter.com/oauth/request_token",
	accessURL="https://api.twitter.com/oauth/access_token",
	authURL="http://api.twitter.com/oauth/authorize")

cred$handshake()

registerTwitterOAuth(cred)

save(file="cred",cred)
<!--:-->

The cred file just created contain all your OAuth data
So you just had to load it and you can authentify yourself with it.

Based on 
https://gist.github.com/stephenturner/3132596
https://github.com/neilfws/Twitter