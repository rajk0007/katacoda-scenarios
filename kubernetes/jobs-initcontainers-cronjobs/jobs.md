[Jobs resources](https://kubernetes.io/docs/concepts/workloads/controllers/jobs-run-to-completion/) are used to running a batch job, supporting parallel jobs until reach a specific number of completions.

Therefore with Jobs, we can run a work items such as frames to be rendered, files to be transcoded, ranges of keys in a NoSQL database to scan, and so on.

Take a look at [Jobs Api reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.11/#job-v1-batch) to see how to build a job resource in Kubernetes.

Pods created by jobs are not deleted. Keeping them around allows you to still view the logs of completed pods to check for errors. If you want to remove them, you need to do that manually.

## Create Countdown Job

Look at the file `job.yaml`{{open}}. 

This example creates a job which runs a bash command to countdown from 10 to 1.

Notice that the field `spec.restartPolicy` just allow two values: "OnFailure" or "Never", for further information read [here](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#example-states)

> **Note:** There're situations where you want to fail a job after some ammount of retries, to do so use `spec.backoffLimit`. It is set by default to 6.
> You could want to manage the duration of the job, not matter how many Pods are created. You can use `spec.activeDeadlineSeconds` and once a Job reaches this value(in sec), the Job and all of its Pods are terminates.

Create the countdown job:

`kubectl apply -f /manifests/job.yaml`{{execute}}

### Job status

Check the status of the job:

`kubectl get jobs`{{execute}}

### Job Logs

In order to see the job's logs we need to get the job name:

`kubectl get pods -o 'jsonpath={.items[0].metadata.name}'; echo`{{execute}}

And then execute the following command to get the logs:

```
kubectl logs `kubectl get pods -o 'jsonpath={.items[0].metadata.name}'` 
```{{execute}}

You will get a result like:

`
9
8
7
6
5
4
3
2
1
Perfect!
`

### Delete Job

`kubectl delete -f /manifests/job.yaml`{{execute}}

or 

`kubectl delete job countdown`{{execute}}