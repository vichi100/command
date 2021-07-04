# command

bash-3.2$ ssh 209.145.57.26@root

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
  mongo -u flicksick -p flicksick123 --authenticationDatabase flicksick_india
  
  
  
  
  
  
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
  
  
