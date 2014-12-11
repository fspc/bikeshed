#BikeShed

**BikeBike Docker Container Image for BikeShed**

Bikeshed is [Velocipede's](http://velocipedebikeproject.org/) User, Sales, and Bike Inventory [Web App](https://github.com/spacemunkay/BikeShed).

##Pull the repository

```
docker pull bikebike/bikeshed
```

##Run the docker container

Publish the container's port to the host:

>format: ip:hostPort:containerPort | ip::containerPort | hostPort:containerPort


```
docker run -d -p 3000:3000 --name="bikeshed" bikebike/bikeshed
```

##Password

Login for test users is on the top website page.

##Special Instructions

Add at least 1 bike to use Desktop View.

##How to test/develop inside the running container process 

This method uses [nsenter](http://jpetazzo.github.io/2014/06/23/docker-ssh-considered-evil/).  Check out [jpetazzo/nsenter](https://github.com/jpetazzo/nsenter) on GitHub. 

```
sudo PID=$(docker inspect --format {{.State.Pid}} <container_name_or_ID>)
sudo nsenter --target $PID --mount --uts --ipc --net --pid
```

