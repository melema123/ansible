# Introduction
This repo contains simple ansible files for automating deployment of [OpenConceptLab]<https://github.com/OpenConceptLab/oclapi>. 
# Files Description
## playbook.yml file 
This file contains three tasks.
1. Clone git repo https://github.com/OpenConceptLab/oclapi.
  The task uses git module provided by Ansible. The repo contains docker compose file that is need to run the application.
2. Copy config file(.env) to the instance.
  Ansible's built in copy module is used by this task. The .env should be manually created on your machine and should not be commited to git as it contains sentitive information. To see the environment variables that need to be configured, please visit https://github.com/OpenConceptLab/oclapi
3. Build and start docker containers. 
  This step uses shell module to run docker-compose command to build and bring up the docker containers. 

## inventory
In this file, I have declared the IP address of the machine where I want the the application to run. I have also declared the location of the ssh key since Ansible will use it to log in to the instance. 
