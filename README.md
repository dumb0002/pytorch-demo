# pytorch-demo


### Deploying LLM-D + Activator

1. Install the Inference Gateway Extension Istio implementation:

    ```shell
    ./1-install-igw.sh
    ```

2. (Optional) Create the namespace and switch to it:

    ```shell
    kubectl create namespace pytorch-demo
    kubectl config set-context --current --namespace=pytorch-demo
    ```

3. Deploy the GIE + EPP + Activator and associated resources:

    ```shell
    kubectl apply -f config/
    ```

4. Verify that the components are deployed and ready:

    ```shell
    kubectl get pods
    ```