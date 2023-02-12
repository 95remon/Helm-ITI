# Helm - Day1

1. Add bitnami helm chart repository in the controlplane node.
    - 
    ```bash
    helm repo add bitnami https://charts.bitnami.com/bitnami
    ```
    ![alt](images/1.png)

2.  - Deploy the Apache application on the cluster using the apache from the bitnami repository.
    - Set the release Name to: amaze-surf
    ```bash
    helm install amaze-surf bitnami/apache
    ```
    ![alt](images/2.png)

3.  Uninstall the apache chart release from the cluster
    ```bash
    helm uninstall amaze-surf
    ```
    ![alt](images/3.png)

4.  - install specfic version of nginx 1.22.0

        - first search for the needed version
        ```bash
        helm search repo nginx --versions
        ```

        - then 
        ```bash
        helm install nginx bitnami/nginx --version 12.0.6
        ```
        ![alt](images/4-1.png)

    - then update it to specfic 1.23.1
        ```bash
        helm upgrade nginx bitnami/nginx --version 13.2.10
        ```

        ![alt](images/4-2.png)

    - then rollback
        ```bash
        helm rollback nginx 1
        ```

        ![alt](images/4-3.png)



