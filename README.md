Prerequisites
To follow this steps, you will need:

One Ubuntu 18.04 server, set up following this Initial Server Setup guide.
Docker installed on your server, following Steps 1 and 2 of How To Install and Use Docker on Ubuntu 18.04.
Node.js and npm installed, following these instructions on installing with the PPA managed by NodeSource.
A Docker Hub account. For an overview of how to set this up, refer to this introduction on getting started with Docker Hub.


Step 1 — Installing Your Application Dependencies
1. mkdir node_project
2. cd node_project
3. create package.json

   "package.json" is already is available in Docker-container folder.
   
4. npm install



Step 2 — Creating the Application Files
1. create app.js
   app,js is already is available in Docker-container folder.
2.Next, let’s add some static content to the application. Start by creating the views directory:

    - mkdir views
    
  Open the landing page file, index.html:
    - views/index.html  
      It is already is available in views folder.
      
3.  For the second page 
    - views/sharks.html
    It is already is available in views folder.
    
4.  For CSS Style 
    - mkdir views/css
    - Create views/css/styles.css
    
5.  To permit traffic to port 8080 run:

     sudo ufw allow 8080
     To start the application, make sure that you are in your project’s root directory:

     cd ~/node_project 
     Start the application with node app.js:

     node app.js
     Navigate your browser to http://your_server_ip:8080.



Step 3 — Writing the Dockerfile
1. Create Dockerfile 
2. Create .dockerignore file 

Now the following commands 

   - docker build -t your_dockerhub_username/nodejs-image-demo .
   - docker images
   - docker run --name nodejs-image-demo -p 80:8080 -d your_dockerhub_username/nodejs-image-demo 

Once your container is up and running, you can inspect a list of your running containers with docker ps:
   - docker ps
   
   With your container running, you can now visit your application by navigating your browser to http://your_server_ip.
