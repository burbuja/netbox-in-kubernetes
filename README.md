# netbox-in-kubernetes

This is a very experimental implementation of NetBox for Kubernetes.

## Prerequisites

* Rook Ceph Block Storage (unless you change it)
* CloudNativePG (unless you change it)
* Ingress-NGINX (unless you change it)

## Installation

Clone this repository:
```sh
git clone https://github.com/burbuja/netbox-in-kubernetes
```

Change the directory:
```sh
cd netbox-in-kubernetes
```

Edit the YAML file:
```sh
nano netbox.yaml
```

Apply it in Kubernetes:
```sh
kubectl apply -f netbox.yaml
```

Wait until the pods are running, then press `Ctrl`+`C` to exit:
```sh
watch kubectl -n netbox get po
```

You'll need to create a super user, then you may want to write the following command:
```sh
kubectl -n netbox exec -it deploy/netbox -- /opt/netbox/netbox/manage.py createsuperuser
```

## License

[Apache License version 2.0](https://github.com/burbuja/netbox-in-kubernetes/blob/master/LICENSE)