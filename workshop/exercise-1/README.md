# Exercise 1 - Accessing your Kubernetes Cluster

You must already have an IBM account, with a cluster created or assigned to you as documented in [previous step](../GETSTARTED.md).

## Connect to your cluster using the Cloud Shell
For this lab, a web shell is provided for you with all the necessary tools. Use this web shell to perform the tasks in this lab. If you are having problems with this web shell, you can use a local docker container and follow the instructions [here](https://github.com/rvennam/istio101/blob/docker-env/workshop/exercise-1/README.md) instead.

1. Using Chrome or Firefox, go to the [Cloud Shell](https://cloudshell-console-ikslab.us-south.cf.cloud.ibm.com/) and login using the Login button.
2. Passcode is `ikslab`
   ![](../README_images/cloudshell.png)
3. Using the account drop down, choose the `IBM` account.
4. Click on the Terminal icon to launch your web shell.

## Access your cluster
Learn how to set the context to work with your cluster by using the `kubectl` CLI, access the Kubernetes dashboard, and gather basic information about your cluster.

1.  Set the context for your cluster in your CLI. Every time you log in to the IBM Cloud Kubernetes Service CLI to work with the cluster, you must run these commands to set the path to the cluster's configuration file as a session variable. The Kubernetes CLI uses this variable to find a local configuration file and certificates that are necessary to connect with the cluster in IBM Cloud.

    a. List the available clusters. You should see the cluster you were assigned.

    ```shell
    ibmcloud ks region-set eu-central
    ibmcloud ks clusters
    ```

    b. Set an environment variable for your cluster name:

    ```shell
    export MYCLUSTER=<your_cluster_name>
    ```

    c. Download the configuration file and certificates for your cluster using the `cluster-config` command.

    ```shell
    ibmcloud ks cluster-config $MYCLUSTER
    ```

    c. *Copy and paste the output export command* from the output of previous step. This will set the `KUBECONFIG` environment variable and configure your `kubectl` CLI to run commands against your cluster. Example:
    `export KUBECONFIG=/Users...`

2.  Get basic information about your cluster and its worker nodes. This information can help you manage your cluster and troubleshoot issues.

    a.  View details of your cluster.

    ```shell
    ibmcloud ks cluster-get $MYCLUSTER
    ```

    b.  Verify the worker nodes in the cluster.

    ```shell
    ibmcloud ks workers $MYCLUSTER
    ibmcloud ks worker-get <worker_ID>
    ```

3.  Validate access to your cluster.

    a.  View nodes in the cluster.

    ```shell
    kubectl get node
    ```

    b.  View services, deployments, and pods.

    ```shell
    kubectl get svc,deploy,po --all-namespaces
    ```

## Clone the lab repo

1. From your command line, run:

    ```shell
    git clone https://github.com/IBM/istio101
    cd istio101/workshop
    ```

    This is the working directory for the workshop. You will use the `.yaml` files that are located in the `workshop/plans` directory in the following exercises.

### [Continue to Exercise 2 - Installing Istio](../exercise-2/README.md)
