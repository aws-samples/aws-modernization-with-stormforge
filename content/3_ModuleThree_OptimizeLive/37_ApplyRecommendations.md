---
title: "Apply Recommendations" 
chapter: false
weight: 7 
---

## Applying Recommendations Using The StormForge UI

With the **StormForge Applier** installed, you can now apply Optimize Live's recommendations directly from the StormForge UI.

If you deployed the StormForge sample application earlier in the workshop, you can navigate back to **"Workloads"** > **"optlive-showcase-app"** (or any other test service on your choice):

![StormForge Applier](../images/stormforge-applier-1350x355.png "StormForge Applier")

Click the **Apply Now** button

Optimize Live will now make the patch available for the StormForge Applier in our cluster and the patch will be applied directly to the workload.

We can confirm that the patch has been applied by running the following command `kubectl rollout history -n <namespace> deploy/<app name>`. For our sample application it would be:
     
     kubectl rollout history -n default deploy/optlive-showcase-app

You should see an output that looks like this:

    deployment.apps/optlive-showcase-app
    REVISION  CHANGE-CAUSE
    1         <none>
    2         Optimize Live (1713298260)

You can see that Optimize Live is listed as the `CHANGE-CAUSE` for the latest rollout.

We can also use the following command to inspect the running configuration of the Pod `kubectl describe pod -n <namespace> <pod name>`, for example:

    kubectl describe pod -n default optlive-showcase-app123456abcde

**Note:** You will want to replace the name of the pod above with the name of the pod in your cluster.

You should see an output that includes the following:

    Limits:
      cpu:     1
      memory:  128Mi
    Requests:
      cpu:        575m
      memory:     12Mi

The new running configuration for the resource `Requests` and `Limits` has been updated to reflect the values provided by Optimize Live.

Finally, we can return to the StormForge UI and see that the patch has been successfully applied.

![StormForge applier time stamp](../images/stormforge-applier-timestamp-1350x278.png "StormForge applier timestamp")

With our Kubernetes workload properly right sized, our workshop is now completed!

You may now continue to explore by deploying and right-sizing additional workloads for the remainder of your 30-day trial of Optimize Live.

### For More Information on Stormforge

* Visit us at [www.stormforge.io](https://www.stormforge.io/?utm_source=AWS&utm_medium=workshop&utm_campaign=AWS%20workshop%202024)

* Sign up for a 30-day free trial of StormForge Optimize Live: [app.stormforge.io/signup](https://app.stormforge.io/signup?utm_source=AWS&utm_medium=workshop&utm_campaign=AWS%20workshop%202025)

* Deploy the StormForge Agent using [EKS Add Ons](https://docs.stormforge.io/optimize-live/getting-started/install-eks-addon/?utm_source=AWS&utm_medium=workshop&utm_campaign=AWS%20workshop%202026)

* If you don't have a cluster, try the StormForge Optimize Live [Sandbox](https://www.stormforge.io/sandbox/?utm_source=AWS&utm_medium=workshop&utm_campaign=AWS%20workshop%202027)

### Next: Cleanup
Proceed to the next step to clean up any resources from this workshop.
