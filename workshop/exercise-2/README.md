
>[Getting Started - Prepare Your Environment](../README.md) ## 
[Exercise 1 - Accessing your Kubernetes Cluster](../exercise-1/README.md) ## 
**Exercise 2 - Installing Istio** ## 
[Exercise 3 - Deploy Guestbook with Istio Proxy](exercise-3/README.md) ## 
[Exercise 4 - Expose the service mesh with the Istio Ingress Gateway](exercise-4/README.md) ## 
[Exercise 5 - Telemetry](exercise-5/README.md) ## 
[Exercise 6 - Traffic Management](exercise-6/README.md) ## 
[Exercise 7 - Security](exercise-7/README.md)

---

# Exercise 2 - Installing Istio on IBM Cloud Kubernetes Service

In this module, you will use the Managed Istio add-on to install Istio on your cluster. 

Managed Istio is available as part of IBM Cloud™ Kubernetes Service. The service provides seamless installation of Istio, automatic updates and lifecycle management of control plane components, and integration with platform logging and monitoring tools.

<!-- Note: Managed Istio has certain hardware (size) requirements. Those requirments are met by the clusters provided to you for this workshop. It is not possible to use managed Istio on the free Kubernetes clusters on IBM Cloud. You can still install Istio manually on a free cluster by following [these instructions](https://github.com/IBM/cloud-native-starter/blob/master/documentation/IKSDeployment.md#add-istio).  -->

1. Run this commmand to install Managed Istio:

    ```shell
    ibmcloud ks cluster addon enable istio --cluster $MYCLUSTER
    ```

2. Run this commmand to check the status of the Istio installation:

    ```shell
    ibmcloud ks cluster addon ls --cluster $MYCLUSTER
    ```

    Once Istio installed successful, output will look similar to this:

    ```
    Name    Version   Health State   Health Status  
    istio   1.4       normal         Addon Ready   
    ```

    If 'Health State' shows "critical", don't panic, just wait a few minutes!

3. Ensure the Istio pods -- especially `istio-citadel-*`, `istio-ingressgateway-*`, `istio-pilot-*`, and `istio-policy-*` -- are all in **`Running`** state before you continue.

    ```shell
    kubectl get pods -n istio-system
    ```
    Sample output:
    ```shell
    NAME                                     READY   STATUS    RESTARTS   AGE
    grafana-6c89cb48cf-v767v                 1/1     Running   0          33s
    istio-citadel-66dff76d4-r9gsf            1/1     Running   0          7m27s
    istio-egressgateway-55fc547574-svkkr     1/1     Running   0          7m27s
    istio-galley-7d9dbfd4b9-fw2qk            1/1     Running   0          7m27s
    istio-ingressgateway-9c4856497-rpxvs     1/1     Running   0          7m27s
    istio-pilot-7ff6949955-d9hbw             2/2     Running   0          7m27s
    istio-policy-6b88dd467b-hxhqx            2/2     Running   1          7m27s
    istio-sidecar-injector-bc8dddd65-bwhbq   1/1     Running   0          7m27s
    istio-telemetry-5f9df6d9cc-wppmf         2/2     Running   1          7m26s
    istio-tracing-5777dc949f-k2lhc           1/1     Running   0          33s
    kiali-8c696cc97-2cwk2                    1/1     Running   0          33s
    prometheus-65c985bf4c-g8ch5              1/1     Running   0          7m26s
    ```

    Before you continue, make sure all the pods are deployed and either in the **`Running`** or **`Completed`** state. If they're in `pending` state, wait a few minutes to let the installation and deployment finish.

    Congratulations! You successfully installed Istio into your cluster.

---

### [Continue to Exercise 3 - Deploy Guestbook with Istio Proxy](../exercise-3/README.md)

