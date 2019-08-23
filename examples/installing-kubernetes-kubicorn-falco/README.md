# Setting up a Kubernetes 1.15.3 cluster with Audit enabled using Kubicorn

Note: this example is running in AWS

### Generate the Cluster Spec

From this directory run:

```bash

kubicorn create falco-cluster -S kubicorn -p aws -M serverPool.bootstrapScripts[0]=kubicorn/amazon_k8s_ubuntu_16.04_master.sh -N serverPool.bootstrapScripts[0]=kubicorn/amazon_k8s_ubuntu_16.04_node.sh

```

Next, set your AWS environmental variables

```

export AWS_ACCESS_KEY_ID=abcabcabcabc
export AWS_SECRET_ACCESS_KEY=123456789

```

Finally apply the cluster

```bash

kubicorn apply cluster falco-cluster -S kubicorn

```
