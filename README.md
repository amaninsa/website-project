# website-project
DEVOPS - Capstone Project

You have been hired as a Sr. DevOps Engineer in Abode Software. They want to
implement DevOps Lifecycle in their company. You have been asked to
implement this lifecycle as fast as possible. Abode Software is a product-based
company and their product is available on this GitHub link.

https://github.com/amaninsa/website-project/

Following are the specifications of the lifecycle:
1. Install the necessary software on the machines using a configuration
management tool
2. Git workflow has to be implemented
3. CodeBuild should automatically be triggered once a commit is made to
master branch or develop branch.
a. If a commit is made to master branch, test and push to prod
b. If a commit is made to develop branch, just test the product, do not
push to prod
4. The code should be containerized with the help of a Dockerfile. The
Dockerfile should be built every time there is a push to GitHub. Use the
following pre-built container for your application: hshar/webapp
The code should reside in '/var/www/html'
5. The above tasks should be defined in a Jenkins Pipeline with the following
jobs:
a. Job1 : build
b. Job2 : test
c  Job3 : prod

















Created a 3 instances in AWS , named master , slave1 and slave2 and configured their security groups for all traffic allowed.





Installed the Ansible on master instance using these commands.



Now configured the slave nodes as worker1 and worker2 inside the /etc/ansible/hosts file .









Now created the ssh keys , using ssh-keygen command in the master node , then copied the id_rsa.pub file to authorized keys of worker1 and worker.






























Authosized keys of worker1 and worker2














Connection established between master and all slaves , checked by pinging the both slaves from master node.




Now Creatd the yaml script file to install the required softwares on the master and slaves nodes.



Acording to script installed java , jenkins , docker on master node and java and jenkins on the slaves nodes.

Instaled required softwares on master 






























Installed required softwares on slaves














Git workflow is implemented , inside the master node.





Configured jenkins inside master node via webconsole , and then configured the 2 nodes , node1 and node2 then connected these nodes with slave1 and slave2.












Node1 and node2 are connected with slave1 and slave2 , at the end master node connected with builtin node.




Now 3 jobs were created inside the jenkins , where 1st job deploying the code from master branch of github repo. to slave1 and then second job deploying the code from develop branch of github repo. to slave2 and finally masterjob deploying code from master branch of  gitub repository to the master node.





We have execute the script in jenkins to automatically the build the docker file everytime whenever there is a change in the project code on github.






Now github-webhook also configured inside the github , so that whenever there is any change inside the github repo. The build automatically get started inside the jenkins.












Now build pipeline plugin installed in jenkins to build the pipeline as per the jobs build one by one, inside the jenkins.
Post build actions also configured inside the masterjob and job1 , so that after their deployment the next will be automatically get deployed.
















On slave1 and slave2 with the help of docker file the webpage the deployed successfully.









