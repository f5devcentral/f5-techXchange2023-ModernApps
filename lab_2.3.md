# Obtain Kubeconfig, deploy app on mk8s and vk8s

The following steps will be performed by AppDev:

## Lab Steps

1. Log into XC Console

1. Navigate to "Distributed Apps"

1. Select **vk8s**

1. Select your vk8s object and Get Kubeconfig

1. Save to project directory

1. Navigate to **Managed K8s**

1. Select your mk8s object, and download the Global Kubeconfig

1. Save to project directory

1. Deploy app to vk8s and mk8s using kubeconfig (from cli)

## Observe

1. Run the following command against all of the clusters:

    ```bash
    kubectl api-resource
    ```

1. Discuss the differences

1. App pod runs on mk8s (App stack cluster) and vk8s (RE based sites) --> use cases discussion

1. Review deployment YAML and compare with outcome in XC Console. Notice replica count on vk8s and mk8s based on manifest

### Takeaways
