---
title: "Deploy the StormForge Agent"
chapter: false
weight: 2 
---

### Sign in to your StormForge account
If you have not already done so, sign in to your StormForge account by visiting [https://app.stormforge.io](https://app.stormforge.io/signup?utm_source=AWS&utm_medium=workshop&utm_campaign=AWS%20workshop%202025)

### Use the "Get Started" Wizard
![get started](../images/stormforge-get-started.png "Stormforge get started")

**1. Enter a cluster name and click Continue**

{{% notice tip %}}
It is not required to match cluster name to the `cluster-name` metadata of your cluster, but it is highly recommended. Run `kubectl config current-context` command in the terminal to retrieve the cluster name you are currently working with, or find it via [AWS Management Console](https://us-west-2.console.aws.amazon.com/eks/home?region=us-west-2#/clusters). 
{{% /notice %}}

![helm values](../images/stormforge-helm-values.png "Stormforge helm values")

**2. Download your Helm values**

![install the agent](../images/stormforge-install-command.png "install the agent")

{{% notice tip %}}
Remember to note the location where you download your helm values file. If you are attending an AWS Event and using Cloud9, you can just drag & drop the downloaded file to the file browser in Cloud9.
{{% /notice %}}

**3. Copy/Paste the preformatted Helm command into your terminal**

    helm install stormforge-agent oci://registry.stormforge.io/library/stormforge-agent \
    --namespace stormforge-system \
    --create-namespace \
    --values <your-values-file.yaml>
You should see an output that looks like this:

    Pulled: registry.stormforge.io/library/stormforge-agent:2.10.4
    Digest: sha256:ad9d473eff1f78839f39d51f29dd528665f38cafa65a3b0d76085685853b78f6
    NAME: stormforge-agent
    LAST DEPLOYED: Mon Apr 15 11:54:40 2024
    NAMESPACE: stormforge-system
    STATUS: deployed
    REVISION: 1
    NOTES:
    ---

    StormForge Optimize Live has been installed!

    If you are installing Optimize Live for the first time, it will take us about
    1 hour to collect enough data to generate your initial recommendations. When
    they're ready, you'll be able to see them at:

    https://app.stormforge.io/

    Having installation issues? To perform a quick health check, try running:

    $ helm test stormforge-agent -n stormforge-system --logs

    Or view our Troubleshooting Guide at:

    https://docs.stormforge.io/optimize-live/guides/troubleshooting/

**4. Congratulations! You have successfully deployed the StormForge Agent**

### Next: Confirm the StormForge Agent is Running 
In the next section, we'll confirm that the StormForge Agent is deployed and reporting metrics back to Optimize LIVE