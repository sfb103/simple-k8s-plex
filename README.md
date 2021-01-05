# simple-k8s-plex
A simple kubernetes deployment for the Plex Media Server

This project works well for a simple deployment, such as a DIY homelab setup, where you'd like to run a Plex Media Server on a kubernetes cluster. This deploys the [plexinc/pms-docker](https://hub.docker.com/r/plexinc/pms-docker/) image from the official Plex Media Server Docker Repo.  By running this media server in a container, it offers better isolation from its host. And by running it on kubernetes, it provides a declartative deployment and rohbustness features, such as liveness probes.

To run this deployment on the kubernetes cluster, simply:
```
kubectl apply -f plex-server.yaml
```
**Note**, This plex server deployment currently assumes it's movies are kept in the ```/mnt/disks/library/videos``` and tvseries are kept in the ```/mnt/disks/library/tvseries```host directories.

Once the plex-server pod is ready on the cluster, you can test that it's available through the web frontend at ```http://your-host:32400/web```.  At that point please refer to the [Plex Media Server documentation](https://support.plex.tv/articles/200264746-quick-start-step-by-step-guides/) for further setup information.
