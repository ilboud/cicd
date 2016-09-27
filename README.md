<<<<<<< HEAD
# Coding the Build

This repository contains the sources used for the presentation that is available at https://codethebuild.github.io/slides/

## Setup you build eco-system
1. Install docker and docker-compose, on Mac use dinghy
  1. When using docker-machine you should create the base directory for the mount points in the vm, see `docker-compose.yml` for the mount points.
  2. An example:
```
docker-machine ssh default
sudo su
mkdir /var/lib/boot2docker/gitlab
mkdir /var/lib/boot2docker/jenkins
mkdir /var/lib/boot2docker/artifactory
mkdir /var/lib/boot2docker/sonar
exit
exit
```
2. Run `docker-compuse up -d` ensure you docker-engine has enought memory. You can also simply start only the services needed. For example `docker-compuse up -d gitlab gitlabrunner`.
3. Register the runner to gitlab.
```
docker exec -i -t gitlab-runner-dind1 gitlab-runner register -n \
   --docker-links 'cicd_gitlab_1:gitlab.docker'
```
4. Login to gitlab, which is available on the port mapped in the docker-compose file or on the dns name docker.gitlab when using dinghy.
5. Login to gitlab using username: "root" and password: "5iveL!fe".
6. Add your own user, setup ssh keys and so on.
7. To run a build create a repository for the sample service and clone the sample service (https://github.com/codethebuild/service) in this repository.
8. Trigger a build by commiting a change or crating ag tag.
=======
This repository contains Dockerfiles for running a set of Continuous Integration Tools with a single command. The tools used in the Docker containers are.
- Jenkins (CI Server)
- Gitlab (SCM)
- Artifacroy (Binaries Repo)
- SonarQube (Code Analysis)

To launcg the stack, clone the repository and run:
docker-compose up -d

You can also start only the services needed. For example 'docker-compuse up -d gitlab jenkins'.

Please modify the mapped volumes and hostnames as needed in the dockercompose.yml file

Access to the CICD Tools:

     Gitlab:      http://127.0.0.1:18080                                                        
                  Login to gitlab using username: "root" and password: "5iveL!fe".              
                  Add your own user, setup ssh keys and so on.                                  
                                                                                                 
    Artifactory:  http://127.0.0.1:18081                                                        
                  Artifactory comes with a pre-configured default "admin" account.              
                  Username: "admin", Password: "password"                                       
                                                                                                 
    Jenkins:      http://127.0.0.1:18082                                                        
                                                                                                 
    SonarQube:    http://127.0.0.1:19000                                                        
                  SonarQube comes with a pre-configured default "admin" account.                
                  Username: "admin", Password: "admin"
>>>>>>> 1e3abb1ec19cfd6f6dc5e13567bd9a8aa94703c8
