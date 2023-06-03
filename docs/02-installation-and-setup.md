# Installation and Setup

To get started with Argo Workflow, we'll walk you through the installation process on your local machine or a Kubernetes cluster. Please note that we won't be using Helm for this installation. Here are the steps to install and set up Argo Workflow:

## Step 1: Install Kubernetes and kubectl:
Before installing Argo Workflow, ensure that you have a working Kubernetes cluster and the kubectl command-line tool configured to interact with the cluster. If you don't have a cluster set up, you can choose one of the following options:

Local Development: Install a local Kubernetes cluster using tools like Minikube or Kind. Follow the documentation for the specific tool to set up the cluster.

Cloud-based Cluster: Create a Kubernetes cluster on a cloud provider such as Google Cloud Platform (GCP), Amazon Web Services (AWS), or Microsoft Azure. Refer to the cloud provider's documentation for instructions on creating a cluster.

## Step 2: Install Argo Workflow Controller:
The Argo Workflow Controller is responsible for managing workflows within the Kubernetes cluster. Follow these steps to install it:

Download the Argo Workflow Controller YAML manifest from the official GitHub repository:

```sh
$ wget https://raw.githubusercontent.com/argoproj/argo-workflows/stable/manifests/namespace-install.yaml
```
Apply the YAML manifest to create the Argo Workflow namespace and resources:
```sh
$ kubectl apply -f namespace-install.yaml
```
Verify that the Argo Workflow Controller components are running:
```sh
$ kubectl get pods -n argo
```
Ensure that the pods are in the "Running" state before proceeding.

## Step 3: Install Argo CLI (Command Line Interface):
The Argo CLI provides a convenient command-line interface to interact with Argo Workflow. Follow these steps to install the CLI:

Download the Argo CLI binary suitable for your operating system from the official GitHub repository:
```sh
$ wget https://github.com/argoproj/argo-workflows/releases/latest/download/argo-linux-amd64.gz
```
Replace argo-linux-amd64.gz with the appropriate binary for your operating system if you're not using Linux.

Unzip the downloaded binary:
```sh
$ gunzip argo-linux-amd64.gz
```
Move the binary to a directory in your system's PATH:
```sh
$ chmod +x argo-linux-amd64
$ sudo mv argo-linux-amd64 /usr/local/bin/argo
```
Verify that the Argo CLI is installed successfully:
```sh
$ argo version
```
You should see the Argo CLI version displayed in the output.

Congratulations! You have successfully installed Argo Workflow and the Argo CLI. You're now ready to start creating and managing workflows using Argo Workflow. In the next sections of this workshop, we'll explore the basics of defining workflows and executing them using Argo Workflow.

Note: If you encounter any issues during the installation process, refer to the official Argo Workflow documentation for troubleshooting steps and additional installation options.
