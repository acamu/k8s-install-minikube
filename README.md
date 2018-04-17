

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

Step 5 - Install minikube

    $ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.26.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/


Dependencies
------------

Install SDL dependency

    $ sudo yum install SDL.x86_64
    $ sudo yum install gcc perl make
    $ sudo yum install sudo yum install linux-headers-$(uname -r)
    $ sudo yum install linux-headers-generic
    
 Install kubectl
 
    $ sudo touch /etc/yum.repos.d/kubernetes.repo

 Into vi add following:
 
    [kubernetes]
    name=Kubernetes
    baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
    enabled=1
    gpgcheck=1
    repo_gpgcheck=1
    gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg

 
    $ sudo yum install -y kubectl
    

Preparing
----------------

    $ sudo /sbin/vboxconfig
    
Check minikube version

    $ sudo ./minikube version
    
Start minikube

    $ sudo ./minikube start

if you are on linux you can use without nested hypervisor

    $ sudo ./minikube start --vm-driver=none

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
[1] https://github.com/kubernetes/minikube
[2] https://continuous.lu/2017/04/28/minikube-and-helm-kubernetes-package-manager/
