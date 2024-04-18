---
title: "Verify the StormForge Agent" 
chapter: false
weight: 3 
---

Using your terminal, use kubectl to get the pods running in the `stormforge-system` namespace.

    kubectl get pods -n stormforge-system
You should see two pods running in the namespace.

    NAME                                                    READY   STATUS    RESTARTS   AGE
    stormforge-agent-metrics-forwarder-99d94f8f8-gcrqk      1/1     Running   0          17s
    stormforge-agent-workload-controller-764f559867-578xz   1/1     Running   0          17s

With the StormForge Agent successfully running in your cluster, we can move to the StormForge web UI.

### Next: Confirm Your Cluster in StormForge UI 
In the next section, we'll confirm that your cluster data is reporting to the StormForge UI