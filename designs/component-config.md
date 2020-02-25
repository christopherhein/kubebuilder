# Component Config in Kubebuilder

Authors: @christopherhein
Last Updated on: 02/24/2020

This document describes the integration of `ComponentConfig` and the patterns for configuring Kubernetes components back into Kubebuilder to reduce the amount of flags that a controller author needs to expose to allow them to customize the internals. This design follows [`ComponentConfig` Controller Runtime]

## Table of Contents

<!--ts-->

<!--te-->

## Summary

## Motivation

This change is important because: 
- 

### Links to Open Issues

- [Implement ComponentConfig by default & stop using (most) flags](https://github.com/kubernetes-sigs/kubebuilder/issues/722)
- [Provide a ComponentConfig to tweak the Manager](https://github.com/kubernetes-sigs/controller-runtime/issues/518)
- [Reduce command line flag boilerplate](https://github.com/kubernetes-sigs/controller-runtime/issues/207)

### Goals

- 

### Non-Goals/Future Work

- 

## Proposal


### User Stories

#### Controller Author with `kubebuilder` (tbd proposal for `kubebuilder`)

- Initialize `kubebuilder` project using `--component-config-name=XYZConfiguration`
- Build custom controller as usual

#### Controller User without modifications to config

_Provided that the controller provides manifests_

- Apply the controller to the cluster
- Deploy custom resources

#### Controller User with modifications to config

- _Following from previous example without changes_
- Create a new `ConfigMap` for changes
- Modify the `controller-runtime` pod to use the new `ConfigMap`
- Apply the controller to the cluster
- Deploy custom resources


### Risks and Mitigations

- 

## Alternatives

* 

## Implementation History

- [ ] 02/24/2020: Proposal submitted to `controller-runtime`
- [ ] 02/26/2020: Proposal submitted to `kubebuilder`

[`ComponentConfig` Controller Runtime]: https://sigs.k8s.io/controller-runtime/designs/component-config.md