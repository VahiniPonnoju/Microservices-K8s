# Microservices-K8s

This is a microservice application built using Flask and deployed on Kubernetes. It is designed to demonstrate how to build and deploy microservices on a Kubernetes cluster

This guide outlines the steps needed to set up a Kubernetes cluster using kubeadm.

# Pre-requisites

Ubuntu OS (Xenial or later) sudo privileges Internet access t2.medium instance type or higher

# Both Master & Worker Node

Run the following commands on both the master and worker nodes to prepare them for kubeadm.

using 'sudo su' is not a good practice. sudo apt update

sudo apt-get install -y apt-transport-https ca-certificates curl

sudo apt install docker.io -y

sudo systemctl enable --now docker # enable and start in single command.

Adding GPG keys.

curl -fsSL "https://packages.cloud.google.com/apt/doc/apt-key.gpg" | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/kubernetes-archive-keyring.gpg

Add the repository to the sourcelist.

echo 'deb https://packages.cloud.google.com/apt kubernetes-xenial main' | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt update

sudo apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y
