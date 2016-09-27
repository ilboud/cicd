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
     Gitlab:       http://127.0.0.1:18080                                                        
                   Login to gitlab using username: "root" and password: "5iveL!fe".              
                   Add your own user, setup ssh keys and so on.                                  
                                                                                                 
     Artifactory:  http://127.0.0.1:18081                                                        
                   Artifactory comes with a pre-configured default "admin" account.              
                   Username: "admin", Password: "password"                                       
                                                                                                 
     Jenkins:      http://127.0.0.1:18082                                                        
                                                                                                 
     SonarQube:    http://127.0.0.1:19000                                                        
                   SonarQube comes with a pre-configured default "admin" account.                
                   Username: "admin", Password: "admin"    