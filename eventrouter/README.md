# Eventrouter

![Docker Pulls](https://img.shields.io/docker/pulls/bdronneau/eventrouter?style=for-the-badge)

Build a public image of [eventrouter](https://github.com/openshift/eventrouter) located at [bdronneau/eventrouter](https://hub.docker.com/r/bdronneau/eventrouter).


## Build

```shell
export GIT_BRANCH=66fc65f

docker build . -t "bdronneau:5.5.0-$GIT_BRANCH" --build-arg GIT_BRANCH=66fc65f
```

## Kubernetes

To deploy this exporter in `kube-system` namespace:

```shell
cd manifest
kubectl apply -k .
```