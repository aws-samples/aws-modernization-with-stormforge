---
title: "StormForge Applier" 
chapter: false
weight: 6 
---

## Should you install the StormForge Applier?
Optimize Live provides a separate application for automatically applying right-sizing recommendations to your Kubernetes workloads on an ad hoc or continuous basis.

Install the StormForge Applier if you plan to:
* **Apply recommendations on demand** from the StormForge UI.
* **Apply recommendations automatically on a schedule.**

![StormForge Applier](../images/stormforge-no-applier-1350x345.png "StormForge Applier")

You do **not** need to install the StormForge Applier if you plan to deploy recommendations as part of a GitOps workflow or export recommendations as patches.

### Install the StormForge Applier

**1. For this workshop, we'll use Helm to install the StormForge Applier:**

    helm install stormforge-applier \
      oci://registry.stormforge.io/library/stormforge-applier \
      -n stormforge-system

**2. To validate the installation, run:**

    kubectl get pods -A | grep 'stormforge-applier'

The output should look something like this:

    stormforge-system    stormforge-applier-8554758f5b-whbc4             1/1     Running   0              20s

**3. Congratulations. You've successfully installed the StormForge Applier**

With the StormForge Applier successfully installed, you can now return to the StormForge UI and apply recommendations with a single click.

### Next: Use the StormForge UI to Apply Right-Sizing Recommendations
Proceed to the next section to learn how to use the StormForge UI and the StormForge Applier to apply right-sizing recommendations to your workloads.