# Istio Helm Charts for OpenShift

Helm charts for deploying Istio into OpenShift.

## Installation Methods

The easiest way to deploy Istio on OpenShift is using the Red Hat OpenShift Service Mesh (OSSM) Operator. However, until Service Mesh v3, coming in Q1 '24, it isn't entirely the same* as upstream Istio.

The next best alternative is using Istioctl with the `--set profile=openshift`. However, this method doesn't "mesh" (I'm sorry) well with clusters managed by GitOps and ACM. Hence the development of these Helm charts!

*Note: technically you can utilize the **Sail Operator** from Red Hat to test OSSM v3 in Dev Preview.

## Helm Chart Development

These charts were developed by reverse engineering the [openshift profile](https://github.com/miethe/istio-helm-ocp/blob/main/manifests/profiles/openshift.yaml).

## Helm Chart Install Steps

All charts should be installed into `-n istio-system` with the exception of istio-cni. This chart should instead be installed into `-n kube-system`. IE: `helm install istio-cni istio/cni -n kube-system`

You can also find these instructions in the README's in the dir of each Chart.
