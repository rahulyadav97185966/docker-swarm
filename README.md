# docker-swarm

This repo is all about the creating nodes and managing that using docker-swarm .
Docker Swarm is basically multi host management tool is different from docker-compose as docker-compose manages multi containers adn this Docker swarm is all about the multiple hosts.
# Why Docker Swarm is Used ?
 Lets's Consider A Scenario that if we have application which is running on docker-compose and as docker-compose is single host that hosts gets down in this case our entire application goes down, hence we use docker swarm as it provides multiple hosts and we can manage our application using it.
 
 # Steps to Configure the Docker Swarm and Launching a httpd container In playwithDocker playground:
    1  docker swarm init --advertise-addr 192.168.0.28 : using this command we make a node as a leader, run this command and you will get one link for the other nodes to join the cluster.Now Copy that link go to different nodes and paste it now that workers work as a worker for this leder 
    2  docker node ls : using this command you can see who is leader and how many workers are there .
    3  docker service create --replicas 3 -p 18080:80 --name test docker.io/httpd  : Now we are going to launch our https application using the below command.
    4  docker service ps test : using this command we can see the service is running and conatiners are running on which worker/Nodes.
    5  docker service scale test = 20 : Using this commmand we can enlarge or redure the replicas of the service.
    6  docker service ps test
  
