# Nomad Cheatsheet

A collection of cheatsheets for getting started with [Nomad](https://github.com/hashicorp/nomad)! 

For the PDF Version of this cheatsheet, click [here](https://www.datocms-assets.com/2885/1650045163-kubernetes-to-nomad-cheat-sheet-v2.pdf).



## Motivation

Learning new tools can be difficult at first, so we wanted curate and collect a series of cheatseheets to help you get started with Nomad. Since kubernetes is popular in the container orchestration world, we felt that the first couple cheat sheets should be focused on nomad commands and concepts from a kubernetes perspective. If you'd like to add to our existing cheatsheets or make new ones, see the [contributing](##Contributing) section below.




## Kubernetes -> Nomad Command cheatsheet 






| What the command does                                                                                                                | Kubernetes                                                                  | Nomad                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Print the logs for a container in a pod or specified resource  | kubectl logs {pod\_identifier}                                                | nomad alloc logs {allocation}                                                                                                                                                                   |
| Get high fidelity information about a cluster resource                                                                               | kubectl describe {resource} {resourceId}                                    | nomad status {identifier}                                                                                                                                                                    |
| Create a resource                                                                                                                    | kubectl {create \| apply} -f {file}                                          | nomad job run {file}                                                                                                                                                                         |
| Stop a resource                                                                                                                      | kubectl delete {resource}                                                  | nomad job stop -purge {job}                                                                                                                                                                        |
| Forward a port locally to your machine                                                                                               | kubectl port-forward {options}                                              | No direct equivalent – See:<br> [hashi.co/nomad-port-fwd](https://hashi.co/nomad-port-fwd) |
| View the machines running in the cluster                                                                                             | kubectl get nodes                                                           | nomad node status                                                                                                                                                                            |
| View the running instances of compute                                                                                                | kubectl get pods                                                            | nomad status {identifier}                                                                                                                               |
| View the documentation for objects                                                                                                   | kubectl explain {resource}                                                 | No equivalent                                                                                                                                                                              |
| Edit API resource in your preferred editor                                                                                      | kubectl edit {resource} *(Via CLI)*                                                   | Edit Jobs in Nomad UI                                                                                                                           | 
| Execute a command in a container                                                                                    | kubectl exec                                                | nomad alloc exec                                                                                                                         | 
Create example workload                                                                                                              |                                                                             kubectl create deployment -- image redis-example -o yaml --dry-run=client| nomad job init                                                                                                                                                                               |
| Open UI for object                                                                                                                   | No direct equivalent. (Kubernetes Dashboard is an optionally available add-on) | nomad ui {identifier}                                                                                                                                                                           |






## Kubernetes -> Nomad Concepts Cheatsheet





| Kubernetes  | Nomad                                        |
| ----------- | -------------------------------------------- |
| Daemon set  | System Job                                   |
| Replica set | Service Job                                  |
| Pod         | Allocation                                   |
| kubelet     | Client Agent (or just “Client”)              |
| Node        | Node (or sometimes “Client” as they map 1:1) |
| Job         | Batch Job                                    |
| CronJob     | Periodic Batch Job                           |





## Contributing


Did we miss one of your favorite commands? We welcome the community to contribute to this repo and insert commands that were helpful for you in your Nomad journey. We also welcome the addition of any new cheatsheets centered around Nomad. If you'd rather not contribute directly, we still encourage you to make an issue outlining what additions you'd like to see.
