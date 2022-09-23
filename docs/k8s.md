---
sidebar_position: 12
---

# K8s

## What is a K8s?
- An orchestation software
- This is the continuous development (CD) part of CI/CD
- A solution to run Docker containers in the cloud in clusters
- Clusters are made up of nodes.
- There are two kinds of nodes
    - Controller Plan
        - Do the work of the cluster
        - Serve the api
        - Watch the server running on the worker nodes to make sure that they don't error out
        - Validates the input asking for a process to be run.  Once the command is validated, the command is added to a tiny db.
        - One of these nodes in the scheduler
            - This looks at the db and schedules the worker nodes to do the task
            - It turns desired states into actual states
            - Once the worker nodes are started, the scheduler watches the nodes to make sure that no nodes crash.  If one crashes, it starts another one
    - Workers
        - Actually run 


## Ephemeral Containers
- Once a container is deleted, there is no trace of that container on the system

