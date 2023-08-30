# EdgeNet | CODECO project
This is an [EdgeNet](https://www.edge-net.org/) repository prepared by the [ATHENA-RC](https://www.athenarc.gr/en/home) team for the WP5 of the [CODECO project](https://he-codeco.eu/).

In the [tutorials](https://github.com/gkoukis/MyTest/tree/main/tutorials) folder we include some ``.yaml`` files EdgeNet provides which enable the utilization of a shared cluster. In there one can find ``.yaml`` files to manage a cluster e.g. [a tenant can assign roles per user](https://github.com/gkoukis/MyTest/blob/main/tutorials/role_binding-ath-admin-george.yaml) or [a user can request a role in a tenant or a subnamespace](https://github.com/gkoukis/MyTest/blob/main/tutorials/rolerequest-ath-george.yaml) or one can form subclusters, creating [slices](https://github.com/gkoukis/MyTest/blob/main/tutorials/sliceclaim-ath.yaml) and [subnamespaces](https://github.com/gkoukis/MyTest/blob/main/tutorials/subnamespace-Workspace-ath.yaml). Check EdgeNet repo [here](https://github.com/EdgeNet-project/edgenet/blob/main/docs/README.md#multitenancy) and [here](https://github.com/EdgeNet-project/edgenet/tree/main/docs/tutorials).

In the [demo](https://github.com/gkoukis/MyTest/blob/main/demo/) folder we include the demo examples prepared by our team during the first 6 months of the CODECO project. There you can find attached the two [``.yaml`` files](https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/), the [*``cdnserviceexample.yaml``*](https://github.com/gkoukis/MyTest/blob/main/demo/cdnserviceexample.yaml) and [*``ping-me-example.yaml``*](https://github.com/gkoukis/MyTest/blob/main/demo/ping-me-example.yaml) to test some basic functionalities of EdgeNet such as the [Selective Deployment](https://github.com/EdgeNet-project/edgenet/blob/main/docs/custom_resources.md#selective-deployment) which allows users deploy pods onto nodes based on their locations. In addition, instructions of the **prerequisites** a user needs to run an experiment on EdgeNet and the **commands** to run the examples are provided, as well as a [**video**](https://github.com/gkoukis/MyTest/assets/127508084/942e05ad-2af0-484e-a80b-f984d562562d) which represents a demo of the deployed ``.yaml`` files.

**[TODO]:** Test the deployment of EdgeNet features in our Kubernetes cluster environment. Check [here](https://github.com/EdgeNet-project/edgenet/blob/main/docs/tutorials/deploy_edgenet_to_kube.md).

**[TODO]:** Comply with EdgeNet instructions for [contributions](https://github.com/EdgeNet-project/edgenet/blob/main/docs/guides/contribution_guides.md).

More information about **EdgeNet** can be found in [EdgeNet-Testbed site](https://www.edge-net.org/pages/running-experiments.html) and the respected [Github](https://github.com/EdgeNet-project/edgenet).
