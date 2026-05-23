Homelab ansible code for a docker swarm cluster with glusterfs storage. Primarily for hosting a atproto PDS. Assumes presence of a Ansible Vault file named "secrets", which obviously is not included.

This will get you most of the way there, but there will be a few manual steps involving setting up the disks and the volume for gluster.

Inspired by and large by https://rpi4cluster.com/docker-swarm-intro/

Will clean up and give a more detailed description as time allows.

Reccomended order of playbooks:
01 - patch.yml (on new machine builds)
02 - docker.yml 
03 - swarm.yml (I start with just one manager and then promote all the nodes to managers. You'll need to put the swarm join token from the first manager into the secrets vault as well.)
04 - gluster.yml (you'll need to format the disks and create the volume manually)
05 - proxy.yml (work in progress)