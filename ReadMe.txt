This was designed as a way to retrieve the most recent tweet by an account (@Dog_Feelings) and display it on a screen. 
Things of note: 
A) This will not show the pinned tweet at the top of the account.
B) This will not show any tweets that were re-tweeted by the account. 

This relies heavily on TwitRSS.me (https://github.com/ciderpunx/twitrssme). 

000-default.conf is configured for a RaspberryPi. Instead of installing FastCGI as ciderpunx has, install libapache2-mod-fcgid, as FastCGI doesn't exist for Raspbian.
