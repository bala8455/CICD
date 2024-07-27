 - Run `./scripts/prepare-release.sh {prod|qa} {release version}`
Example: `./scripts/prepare-release.sh prod 1.6`
 - Upack the release archive to the desired location. 
Example: `tar -xf release-1.6.tar.gz -C ~/code`
 
 - Navigate to the release location:
Example `cd ~/code/release`
 
 - Run the web application in the background using the `server.sh` script : 
`./server.sh start`
- Wait until the log line containing `ACCEPTING_TRAFFIC` is displayed and press any key to return to the terminal
 - Test that the web application is running and healthy: `curl http://127.0.0.1:8081/status`
Example response: `OK`
- Test the the web application was deployed with the right configuration (environment and release):  `curl http://127.0.0.1:8081/version`
Example response: `Environment: PROD, Version: 1.6`
- Stop the web application using the server.sh script: 
  `./server.sh stop`