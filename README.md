# OpenShift Examples - SOLR
Example simple SOLR search running on Open Shift

Requires the [OpenShift SOLR S2I builder image](https://github.com/dudash/openshift-solr)

To run it:
`oc new-app dudash/openshift-solr~https://github.com/dudash/openshiftexamples-solrdemo.git --name=solr-demo -e CORE_NAME=configset-ex`

The above command pulls the `openshift-solr` docker image from Docker Hub (to use as a builder), then it fetches the code from the referenced github URI, then it creates all the resources needed for Kubernetes and OpenShift, then it does a SOLR specific build, then it containerizes the build results, and then it deploys that built image into your cluster.

Results will look something like:
```
--> Found Docker image 8b8233a (21 hours old) from Docker Hub for "dudash/openshift-solr"

    SOLR 6.4 
    -------- 
    Run SOLR search in OpenShift

    Tags: builder, solr, solr6.4

    * An image stream will be created as "openshift-solr:latest" that will track the source image
    * A source build using source code from https://github.com/dudash/openshiftexamples-solrdemo.git will be created
      * The resulting image will be pushed to image stream "solr-demo:latest"
      * Every time "openshift-solr:latest" changes a new build will be triggered
    * This image will be deployed in deployment config "solr-demo"
    * Port 8983/tcp will be load balanced by service "solr-demo"
      * Other containers can access this service through the hostname "solr-demo"

--> Creating resources ...
    imagestream "openshift-solr" created
    imagestream "solr-demo" created
    buildconfig "solr-demo" created
    deploymentconfig "solr-demo" created
    service "solr-demo" created
--> Success
    Build scheduled, use 'oc logs -f bc/solr-demo' to track its progress.
    Run 'oc status' to view your app.
 ```


![Screenshot](./.screens/2017-03-11.png?raw=true)
