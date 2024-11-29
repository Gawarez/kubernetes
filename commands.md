# Creating a ConfigMap (CM) for .envs

```
kubectl create configmap my-config --from-env-file=.env
```

## Using the CM

```
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: my-container
    image: my-image
    envFrom:
    - configMapRef:
        name: my-config
```

# Creating a Secret for Docker Login (config.json)

```
cat ~/.docker/config.json | base64

kubectl create secret generic regcred -n namespace \
  --from-file=.dockerconfigjson=<path/to/.docker/config.json> \
  --type=kubernetes.io/dockerconfigjson
```
