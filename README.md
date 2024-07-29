# Helm Chart

Add the repo to Helm and update.

```
helm repo add kerwood https://kerwood.github.io/helm-charts
helm repo update
```

List charts available.

```
$ helm search repo kerwood
NAME                                    CHART VERSION   APP VERSION     DESCRIPTION
kerwood/az-group-controller             1.0.0           v0.1.0          Reconciles group information from Azure to Kube...
kerwood/pubsub-push-config-injecter     1.0.0           v1.0.0          Admission controller for injeting a pushConfig ...
```

## Azure Group Controller

A Kubernetes controller that creates a `AzureGroup` resource with a list of members and some basic information on the group.  
The controller will continuously reonconsile the `AzureGroup` resource.

https://github.com/Kerwood/azure-group-controller

## PubSub Push Config Injecter

When deploying a Google Cloud PubSubSubscription with a pushConfig using Config Connector in GKE, the `pushConfig.endpoint` value can contain credentials.
This little application is a Kubernetes Admission Controller that mutates the PubSubSubscription object and injects the `pushConfig.endpoint` value from a secret.

https://github.com/Kerwood/pubsub-push-config-injecter
