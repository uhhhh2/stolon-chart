# About this fork
The point of this fork is to figure out how to get the stolon chart working on Kubernetes 1.6. The original 
README follows...

# Helm chart to install Stolon (HA PostgreSQL cluster)

> Stolon is a cloud native PostgreSQL manager for PostgreSQL high availability.
> It's cloud native because it'll let you keep an high available PostgreSQL inside your containers
> (kubernetes integration) but also on every other kind of infrastructure
> (cloud IaaS, old style infrastructures etc...)

Chart is partially based on the statefullset example from the [stolon repo](https://github.com/sorintlab/stolon/tree/master/examples/kubernetes/statefulset)

Currently only etcd backend is supported.
Etcd is based on [chart from incubator](https://github.com/kubernetes/charts/tree/master/incubator/etcd) with updates to support 1.5 statefulset (PR pending).
After it will be merged, etcd will be removed from the source. 


## Requirements
* Kubernetes >1.5, <1.6
* PV support on the underlying infrastructure
* Helm 2.2.0 (for `conditions and flags` support)


## TODO:
- [x] automate initial stolon cluster creating
- [ ] Managed and standalone mode for etcd
- [ ] Try to integrate etcd operator
- [ ] Add support for consul backend
- [ ] Conditional dependencies to be able to use either etcd or consul
- [ ] Add support for 1.6


## Known issues
* etcd from the incubator(and the copy here) has problems with **scale down** and re-joining fallen pods. [#685](https://github.com/kubernetes/charts/issues/685)

 
