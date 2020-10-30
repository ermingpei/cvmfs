
There are different approaches to enalbe CVMFS on a cloud, either install & configure directly on a running VM, 
or add a Customzation Script when launching a VM, or even apply it to your own cloud image(s). 

Here is the script and the snapshot of the dashboard:

```
#!/bin/bash

sudo yum -y install https://ecsft.cern.ch/dist/cvmfs/cvmfs-release/cvmfs-release-latest.noarch.rpm
sudo yum -y install https://package.computecanada.ca/yum/cc-cvmfs-public/prod/RPM/computecanada-release-latest.noarch.rpm
sudo yum -y install cvmfs cvmfs-config-default cvmfs-config-computecanada cvmfs-auto-setup

cat << EOF > /etc/cvmfs/default.local
CVMFS_REPOSITORIES="cvmfs-config.computecanada.ca,soft.computecanada.ca,soft.galaxy,soft.mugqic" 
CVMFS_STRICT_MOUNT="yes"
CVMFS_QUOTA_LIMIT=10000 # Adjust this value according to the storage space on the VM
CVMFS_HTTP_PROXY="http://cvmfs-cache.arbutus.cloud.computecanada.ca:3128;DIRECT"  #Recommended to use a local squid (CVMFS caching service)
EOF

```

![Alt Install_CVMFS_on_your_VM](https://user-images.githubusercontent.com/73720293/97760381-a80ae600-1ac8-11eb-904f-5861c93d6bd8.png)

