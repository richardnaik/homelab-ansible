Homelab ansible code for a docker swarm cluster with glusterfs storage. Assumes presence of a Ansible Vault file named "secrets", which obviously is not included.

This will get you most of the way there, but there will be a few manual steps involving setting up the disks and the volume for gluster.

Inspired by and large by https://rpi4cluster.com/docker-swarm-intro/

Will clean up and give a more detailed description as time allows.

Reccomended order of playbooks:
patch.yml (on new machine builds)
docker.yml
swarm.yml (I start with just one manager and then promote all the nodes to managers)
gluster.yml (you'll need to format the disks and create the volume manually)