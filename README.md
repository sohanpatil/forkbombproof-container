# Why is Docker Secure ? 
CGroups are used by Docker to limit the usage of system resources. This includes limiting memory usage, number of processes created, etc. </br>
Through creating a Docker like container using **Linux namespaces and CGroups**, I tried to see how Docker could provide process isolation and prevent malicious attacks from inside the containers.</br>

command to run :- **go run main.go run [x]** </br>
[x] could replace /bin/bash, or any other process. This [x] process will run in an isolated container with it's own root mount, hostname and process space. The limit to processes is 20, hence a fork bomb will be avoided.</br>

Fork bombing - Please try carefully and in the container's context</br>
command to run (in containerized /bin/bash) :- **:(){ :|: & };:**

(Inspired by https://gotoams.nl/2018/sessions/429) 
