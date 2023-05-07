I've made some modifications for dockerization. To start up the container, just:
1. `cd docker`
2. `docker-compose up -d --build`
3. `docker exec -ti nanogpt bash`

This will start a container which with all of the dependencies required for running nanogpt
Should you desire to run any jupyter notebooks, you will need to start jupyter in a way that makes it easily accessible from outside of the container. 
To accomplish this, I've added the short script: `start_jupyter.sh`
After running this script, you should be able to see jupyter by pasting this url in your browser: http://localhost:8888/?token=


