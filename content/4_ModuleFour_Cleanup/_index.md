---
title: "Cleanup"
chapter: true
weight: 4
---

# Cleanup

## Uninstall StormForge Agent and Applier
To uninstall the **StormForge Applier**, run the following command:

    helm uninstall stormforge-applier -n stormforge-system

To uninstall the **StormForge Agent**, run the following command:

    helm uninstall stormforge-agent -n stormforge-system

## Uninstall the StormForge Sample App
To uninstall the **StormForge Sample App**, run the following command:

    helm uninstall optlive-showcase-app -n default

## Cleanup your EKS Cluster
If you created a cluster as part of this workshop:
* Clean up instructions on [EKS Workshop](https://www.eksworkshop.com/docs/introduction/setup/your-account/cleanup)

### Workshop Completed!

![StormForge Thank You](images/stormforge-thankyou-375x340.png "StormForge Thank You")
