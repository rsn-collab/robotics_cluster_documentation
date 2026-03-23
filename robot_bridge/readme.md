# Setup Robot Bridge on TACC

---

We are going to use the dockwater:humble image but convert it into a SIF image for Apptainer to use on the TACC compute node.

Assuming you are on a compute node (see `idev` instructions in the main readme)

1.

```bash

module load tacc-apptainer/1.4.1
```

1. Pull docker image using apptainer.

> [!CAUTION]
> This points to a docker image registered on Tanay's dockerhub. If you want to make changes then modify the Dockerfile and push it to your own Dockerhub using `docker push`

```bash
apptainer pull $WORK/ros_gazebo.sif docker://tanay575/dockwater:humble
```

1. Enter a tmux session and launch the Apptainer container

```bash

bash robot_bridge/launch_apptainer.sh
```

This should do the job of either launching the container or joining an already running container.
