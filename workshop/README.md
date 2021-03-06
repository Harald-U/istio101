


# Getting Started


## Prepare Your Environment

In this section, you will login to your own IBM Cloud account, and then get access to an IBM Cloud Lab account which contains pre-provisioned Kubernetes clusters. Each lab attendee will be granted access to one cluster.

1. Create your own [IBM Cloud account](https://ibm.biz/BdqcXN)   

1. After the email verification, confirm by logging in to [https://cloud.ibm.com](https://cloud.ibm.com).

1. Go to [IBM Cloud Lab](https://istio1010bin.mybluemix.net/) web page and enter your IBM ID (the email you used to sign up) and the lab key (should be written on the whiteboard) from the instructor, accept the t&c's

    ![](README_images/get-clusters-no-region.png)

1. You will be added to the IBM Lab account and granted access to a cluster. Note the name of your cluster. It will be something like: `istio1010binXX`.

1. Refresh your [IBM Cloud Dashboard](https://cloud.ibm.com)

1. Switch to the **1840867-IBM** account by clicking on the account selection drop down in the top nav bar.

   ![](README_images/ibmaccount.png)

1. Click on **Clusters** in the Resource Summary tile.

    ![](README_images/dashboard.png)

1.  Under **Clusters**, click on the cluster that has been assigned to you.

    ![](README_images/resource_list.png)

1. Launch the **Kubernetes Dashboard** and have a look around! You can come back to this dashboard throughout your lab.

10. On your own workstation/laptop/notebook create a text file (call it 'environment.txt' if you need an idea for a name) and save the cluster name ('export MYCLUSTER=...'). Keep this **environment file** open throughout the lab to store or access important values and parameters.

    You can use this as a template for your own `environment.txt`:

    ```
    Access the K8s cluster:
    export MYCLUSTER=
    ibmcloud ks cluster config $MYCLUSTER
    export KUBECONFIG=

    Get the Workshop code:
    git clone https://github.com/Harald-U/istio101.git
    cd istio101/workshop/guestbook/v2

    Tone Analyzer (you may need to change istio101/workshop/guestbook/v2/analyzer-deployment.yaml again)
    apikey: 
    url:    
    ```


11. Now continue with the exercises. You need to complete exercise 1 through 4 in sequence: 

    - [Exercise 1 - Accessing your Kubernetes Cluster](exercise-1/README.md) 
    - [Exercise 2 - Installing Istio](exercise-2/README.md)
    - [Exercise 3 - Deploy Guestbook with Istio Proxy](exercise-3/README.md)
    - [Exercise 4 - Expose the service mesh with the Istio Ingress Gateway](exercise-4/README.md)

    Exercises 5 through 7 can be done in any order:

    - [Exercise 5 - Telemetry](exercise-5/README.md) 
    - [Exercise 6 - Traffic Management](exercise-6/README.md) 
    - [Exercise 7 - Security](exercise-7/README.md)


