# nginx: Test Helm Chart

This Helm chart provides examples of some of Helm's more powerful
features.

**This is not a production-grade chart. It is an proof-of-concept example**

The chart installs a simple nginx server according to the following
pattern:

- A `ConfigMap` is used to store the files the server will serve.
  ([templates/configmap.yaml](templates/configmap.yaml))
- A `Deployment` is used to create a Replica Set of nginx pods.
  ([templates/deployment.yaml](templates/deployment.yaml))
- A `Service` is used to create a gateway to the pods running in the
  replica set ([templates/service.yaml](templates/service.yaml))

The [values.yaml](values.yaml) exposes a few of the configuration options in the
charts, though there are some that are not exposed there (like
`.image`).

The [templates/_helpers.tpl](templates/_helpers.tpl) file contains helper templates. The leading
underscore (`_`) on the filename is semantic. It tells the template renderer
that this file does not contain a manifest. That file declares some
templates that are used elsewhere in the chart.

Helpers (usually called "partials" in template languages) are an
advanced way for developers to structure their templates for optimal
reuse.

To deploy this chart, just checkout this repo and browse to the root of the repo.
Type helm install nginx
To initialize an empty repo instead, type helm create <chart-name>

