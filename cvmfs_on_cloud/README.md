

There are different approaches to enable CVMFS on a cloud, either by adding a Customzation Script when launching a VM, or install & configure directly on a running VM, or even apply it to your own cloud image(s). 

Here is the script and the snapshot of the dashboard:

![CVMFS Custmozation Script](https://raw.githubusercontent.com/ComputeCanada/cvmfs/main/cvmfs_on_cloud/customization_script_CtosRH)


![Alt Install_CVMFS_on_your_VM](https://user-images.githubusercontent.com/73720293/97760381-a80ae600-1ac8-11eb-904f-5861c93d6bd8.png)

(Note that the above script works only for CentOS/Redhat/Fedora OS flavors. TBD for Ubuntu/Debian/Windows users.)  


You may also run the script on your VM. 


Once it's installed and configured, you can test CVMFS with running:

```
$ ls /cvmfs/soft.computecanada.ca
config  custom  easybuild  gentoo  new_repository  nix
```

or list any other repositories you added to CVMFS_REPOSITORIES variable. 


Once CVMFS is set up, you can run the following command to enable software modules from CVMFS:

`$ source /cvmfs/soft.computecanada.ca/config/profile/bash.sh`

More details please refer to: https://docs.computecanada.ca/wiki/Accessing_CVMFS





