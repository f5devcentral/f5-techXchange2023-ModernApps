### Obtain Kubeconfig, deploy app on mk8s and vk8s

The following steps will be performed by AppDev

### Lab Steps
  - Log into XC Console, navigate to "Distributed Apps" --> vk8s --> (select your vk8s object) --> Get Kubeconfig --> Save to project directory
  - Navigate to "Managed K8s" --> <select your mk8s object> --> Get Kubeconfig --> Save to project directory
  - Deploy app to vk8s and mk8s using kubeconfig (from cli) 

## Observe
- Run `kubectl api-resource` against all of the clusters.
- Discuss the differences
- App pod runs on mk8s (App stack cluster) and vk8s (RE based sites) --> use cases discussion
- Review depoyment YAML and compare with outcome in XC Console. Notice replica count on vk8s and mk8s based on manifest 

### Takeaways
