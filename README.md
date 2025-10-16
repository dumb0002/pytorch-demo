# pytorch-demo


### Deploying LLM-D + Activator

1. Install the Inference Gateway Extension Istio implementation:

   a) Install:
    ```shell
    ./install-igw.sh
    ```

   b) Verify that the components are deployed and ready:
   ```shell
   kubectl -n istio-system  get pods
   ```
   
   Expected output:
   ```console
    NAME                      READY   STATUS    RESTARTS   AGE
    istiod-7477bbf4cc-mltq4   1/1     Running   0          49s
   ```

2. (Optional) Create the namespace and switch to it:

    ```shell
    kubectl create namespace pytorch-demo
    kubectl config set-context --current --namespace=pytorch-demo
    ```

3. Deploy the EPP + Activator and associated resources:

   a) Install: 
    ```shell
    kubectl apply -f config/
    ```

    b) Verify that the components are deployed and ready:

    ```shell
    kubectl get pods
    ```
    Expected output:
    ```console
    NAME                                      READY   STATUS    RESTARTS   AGE
    granite-3-2b-activator-5cf4948dff-ngn7d   1/1     Running   0          14s
    granite-3-2b-epp-75d888d66f-c6kff         1/1     Running   0          14s
    sza-istio-567ff7fb88-dfjm8                1/1     Running   0          14s
    ```