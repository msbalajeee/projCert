This project has clone of edureka-devops/projCert codes.
Additionally ansible playbooks are created to install puppet agent and docker on "worker" node
The node name is hardcoded currently, but it will be ignored when called via. Jenkins pipeline.

How to use:
1. In jenkins master clone the repo
2. Execute ansible-playbooks
      a. You should have configured "worker" node earlier with python, openssh-server and git
      b. You should have created ssh keys and updated the keys in jenkins credential manager
      c. created user should have sudo privilages to install softwares
3. Execute jenkins job to clone the repo to slave server (worker node)
4. Execute docker build to "build image" using Dockerfile (ex: docker build -t mytest .)
5. Start the container ( docker run -p 8080:80 -d mytest )
6. Test using "curl http://localhost:8080" should show the output. Accessing via. chrome or other browser may not work due to SSL issues
