# OpenShift Examples - SOLR
Example simple SOLR search running on Open Shift

Requires the [OpenShift SOLR S2I builder image](https://github.com/dudash/openshift-solr)

To run it:
`> oc new-app dudash/openshift-solr~https://github.com/dudash/openshiftexamples-solrdemo.git --name=solr-demo`

The above command pulls the `openshift-solr` docker image from Docker Hub (to use as a builder), then it fetches the code from the referenced github URI, then it creates all the resources needed for Kubernetes and OpenShift, then it does a SOLR specific build, then it containerizes the build results, and then it deploys that built image into your cluster.