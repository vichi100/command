# command

bash-3.2$ ssh root@209.145.57.26

# node js / expo / yarn  env setup on mac

$ sudo npm install --global expo-cli
$ npm install --global yarn

# Utility commands

$ netstat -ltnp
$ netstat -ltnp | grep -w ':80'
$ sudo service nginx stop
$ sudo service nginx start
$ sudo nginx -t

$ pm2 start app.js
$ pm2 show app
$ pm2 status
$ pm2 restart app
$ pm2 stop app
$ pm2 stop all
$ pm2 logs (Show log stream)
$ pm2 flush (Clear logs)
$ pm2 monit

# To start react js web app
$ pm2 start npm -- start

# To make sure app starts when reboot
pm2 startup ubuntu / centos

$ npm start // to start node js app
$ expo start  // to start expo project

$ grap vichi <file-name> | grep rajan
$ zgrap vichi <file-name> | grep rajan
$ ssh root@<host-ip-address> to connect from terminal


# install node js
  https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-centos-8
  
 
  npm install --global yarn
  
# install mongodb
  https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-centos-8
  https://matteocontrini.medium.com/how-to-setup-auth-in-mongodb-3-0-properly-86b60aeef7e8

URLs:

Run Multiple Site from one IP with reverse proxy Nginx:  https://www.youtube.com/watch?v=x1fnOJsX6wE. j38DS7x9smN54Tp   209.145.57. 
  
Node app deploy with nginx & SSL:  https://gist.github.com/bradtraversy/cd90d1ed3c462fe3bddd11bf8953a896 
  
Run multiple nodejs app in same server with different domain and run all app concurrently:    https://gist.github.com/hasibdesk/f508d7e1a101109a2e1c3e23c058c33b
  
  
Redirect users to iTunes app store or google play store:
  
  https://stackoverflow.com/questions/35430336/redirect-users-to-itunes-app-store-or-google-play-store
  
  https://www.onelink.to/
  
  
 TMDB
  https://www.themoviedb.org/documentation/api/wrappers-libraries
  
  https://rapidapi.com/movie-of-the-night-movie-of-the-night-default/api/streaming-availability
  
  # mongo
	adminvichi vichi123
	flicksick_india -> flicksick, flicksick123
	Command to connect shell : mongo -u flicksick -p flicksick123 --authenticationDatabase flicksick_india

# To start mongodb server
  	sudo service mongod start
	sudo service mongod status
	Note: if find any connection timeout / connection refuse erro check binding in /etc/mongod.conf file make it to 0.0.0.0 host
  
  
# Mongo db util query
	show dbs
	use <db name>
	show collections
  
# Python
	
	run python file: python3 stream.py
	pip3 install omdb
 
	
	
	
	
# FLICK SICK DATABASE SETUP SETPS
	1) Run stream.py : python3 stream.py , this will setup movies collection
	2) Run omdbTest.py: python3 omdbTest.py , this will set rating array in movies collection's document
	3) Run category.js: node category.js, this will create collections for diffent category.
	4) Run utilx.js: node utilx.js, this will create utils collection.
	5) Run ottProvider.js: node ottProvider.js, this will setup ott provider in utils collection
	6) Run trending.js: node trending.js, for diffrent pages, this will print id of trending movies.
	7) from step 6 copy trending movies ids to trending.py and run trending.py: python3 trending.py, this will create tmdb_trendings collection.
	8) Go to flicksickapp.com/trending and categories trending movies to friend / trending, this will create homedatas collection.
  
	
# App Over-the-Air
	https://www.youtube.com/watch?v=Si909la3rLk
	https://medium.com/@vinod8812/integrate-codepush-with-react-native-for-over-the-air-app-update-bb200683a173
	https://appcenter.ms/
	https://pagepro.co/blog/react-native-over-the-air-updates/
	
	
# One link for AppStore and PlayStore
	https://www.onelink.to/#editor
	
	
	
# process.json
  {
  "apps": [
    {
      "name": "FLICK SICK API SERVER",
      "cwd": "./flicksick_app_server", // this is directory url of your app
      "script": "npm start",
      "env": {
        "NODE_ENV": "production"
      }
	},
	{
      "name": "FLICK SICK WEB SERVER",
      "cwd": "./flicksick_web_server", // this is directory url of your app
      "script": "npm start",
      "env": {
        "NODE_ENV": "production"
      }
    },
    
  ]
}
  
  
# ngix config
	
	sudo nano /etc/nginx/conf.d/flicksick.com.conf

	server {
    server_name flicksickserver.com www.flicksickserver.com;

    location / {
        proxy_pass http://localhost:3050; #whatever port your app runs on
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
