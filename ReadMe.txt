This was designed as a way to retrieve the most recent tweet by an account (@Dog_Feelings) and display it on a screen. 
Things of note: 
A) This will not show the pinned tweet at the top of the account.
B) This will not show any tweets that were re-tweeted by the account. 

This relies heavily on TwitRSS.me (https://github.com/ciderpunx/twitrssme). 

000-default.conf is configured for a RaspberryPi. Instead of installing FastCGI as ciderpunx has, install libapache2-mod-fcgid, as FastCGI doesn't exist for Raspbian.

Installation (Raspberry Pi - Raspbian Buster)

1. Install Apache2
2. Install TwitRSSMe (https://github.com/ciderpunx/twitrssme)
3. Place 000-default.conf in /etc/apache2/sites-enabled
4. Place index.html and thought_bubble.png in /var/www/html
5. Restart Apache2 service

TwitRSSMe Raspberry Pi Install Notes

Follow the Install.MD file instructions with the following caveats:
- install fcgid instead of FastCGI (liapache2-mod-fcgid)
- apt-get install cpanminus libcurl13-dev
- cd /var/www/twitrssme before running cpanm --installdeps
- Until https://github.com/ciderpunx/twitrssme/issues/75 is resolved - edit /var/www/twitrssme/fcgi/twitter_user_to_rss.pl and add 
	$browser->cookie_jar( {} ); 
  between line 24 and 25. 
    -edit /var/www/twitrssme/index.html and replace mobile_twitter_to_rss with twitter_user_to_rss
