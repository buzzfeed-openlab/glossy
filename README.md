# glossy
##audio annotation for webvr
Glossy is an in-progress prototype for audio annotation in VR in the browser. It uses websockets to propagate new annotations to all clients, and saves annotations to a database (I am using MongoDB) as a BLOB and xyz information. Existing database entries are propagated when a client first loads the page.
##some notes
- Web audio requires an https address, getUserMedia won't run on insecure origins. This means you'll need an SSL certificate... you could use Let's Encrypt or self-signed certificate. 
- Because i am testing this in vive, which requires a windows PC, i have found it useful to host the project on a remote server so that I can develop on my non-windows computer. 
- The database I am using is currently MongoDB.
- To run the program in an HTC vive, it's necessary to use a version of Chromium that supports webvr. There is a chrome plugin for testing but it currently breaks the page, maybe it will be resolved soon :).

##running Glossy
You need a windows machine, an HTC Vive, a recent build of Chromium that supports webVR (You may have to run with webvr flags), and an https server. You will have to install MongoDB and mongoose on the server, and other dependencies. Run node index to get an error indicating which are required, and install them (npm install xxx). If you want to look at the code in a regular browser, it will open and run in chrome. Hotkeys "K" and "L" will allow you to test out the start and stop audio recording. 
- The main script is in index.html, and the server code is in index.js. Dependencies are made visible in "public". 
- Server configs (called glossy in configs) shows what I used to make socket.io, ec2, nginx, and node work together on Ubuntu 16.04
- Give it a minute to load, it's a bit slow when loading many files. 
- if you want to test this in my production environment just email me at sutherlande@gmail.com and I will make sure it's working and send you the link.
- if you are running locally, it will run in localhost:3000, and the Mongodb is located in port 27017.


##ToDo
- add "selecting" functionality
- add "groups" to annotations

