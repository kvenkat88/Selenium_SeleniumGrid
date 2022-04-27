#### Points to Remember
- Refer this file for docker-compose-hub-grid.yml for Selenium Grid Setup or Selenium Paralell Execution
- Fully defined process and healthcheck mechanism is implemented for validating nub(Master) and nodes(slave machines/browser nodes)
  for parallel browser execution in different OS Platforms.
- As of now, we have implemented for Linux Platform and we can extend to other platforms like Windows and MAC.
- As of now, we have implemented chrome,firefox and edge browsers for Linux Platform.
- We can customize the browser nodes based upon the available env options as per Selenium Docker implementation. We have included the 
  env options available as well for hub and nodes.
- Activities like building the docker image, running the docker images are all automated using docker-compose and available in gitlabci.yml file.
- We can view the browser execution videos by navigating to path CICD_SERVER path - /tmp/videos. In docker compose file volume mounted path is /tmp/videos:/videos for each of the browser nodes.
- We can also view the test execution process for each browser using NO_VNC port configured for browser node. Ports exposed are 9001 for chrome, 9002 for edge and 9001 for firefox.
  We can access this tunneling the ports and view in browser like http://localhost:9001
- Access Selenium Hub/Master/Selenium Grid using the url - http://localhost:7777/ui/index.html
- Access Selenium Hub/Selenium Grid health status using the url - http://localhost:7777/status
- Always try to use the latest browser nodes by referring the docker-selenium page. 

#### Manual Setup or Execution
  
- Building Services - **docker-compose -f docker-compose-hub-grid.yml up --build -d**
- Stop and clear the services - **docker-compose -f docker-compose-hub-grid.yml down**

#### Test Artifacts Collection
  
- Test artifacts are collected for all browser nodes and upload as part of the pipeline job running.
- Difficulty - There is no proper test reporting technique available in pytest or python for fetching the separte browser node execution. In Java Selenium we have this flexibility.

