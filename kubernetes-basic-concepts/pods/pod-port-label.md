## Tasks

1- Add three labels:
```
app: nginx
segment: frontend
company: contino
```
2- Configure 80 port:
```
ports:
      - name: web
        containerPort: 80
        protocol: TCP
```
3- Modify docker image to the following one:
```

```


**Here is how looks like the pod frontend after the modifications:**

```
apiVersion: v1
kind: Pod
metadata:
  name: frontend-pod
  namespace: contino
  labels:
    app: nginx
    segment: frontend
    company: contino
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - name: web
      containerPort: 80
      protocol: TCP
```

**To deploy it run the folllowing command:** 

`kubectl apply -f frontend-pod2.yaml`{{execute}}

## Validation

**Describe frontend pod up:**

`kubectl describe pod frontend-pod2 --namespace contino`{{execute}}