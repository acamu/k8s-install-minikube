

# k8s-install-minikube
------------

### Description
This tuturial will explain how to deploy a minikue cluster on a VMWare hosted image

Requirements
------------

Step 1 — Unable VT-X
In the VMware setting of the image set the preference to VT-X and check VTX/ETP

Step 2 - Update system

    $ sudo yum update
    $ sudo yum upgrade

Step 3 - Install an Hypervisor

    $ curl -Lo VirtualBox-5.2-5.2.8_121009_el7-1.x86_64.rpm https://download.virtualbox.org/virtualbox/5.2.8/VirtualBox-5.2-5.2.8_121009_el7-1.x86_64.rpm
    $ sudo rpm -ivh VirtualBox-5.2-5.2.8_121009_el7-1.x86_64.rpm --replacepkgs
    
Step 4 - Install kernel header 

    $ sudo yum install "kernel-devel-uname-r == $(uname -r)"

Dependencies
------------

Install SDL dependency

    $ sudo yum install SDL.x86_64
    $ sudo yum install gcc perl make
    $ sudo yum install sudo yum install linux-headers-$(uname -r)
    $ sudo yum install linux-headers-generic
    

Preparing
----------------

    $ sudo /sbin/vboxconfig
    

Testing
----------------



License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

Contributors
------------


References
-----------
[1] xxx
