# Overview

This is an example of a namespace repo with multiple locations embedded. This could be used by a region or market

# NOTE

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: dis-is-a-test # GIVE THIS A NAME
  labels:
    app: hello
    # CREATE A LABEL OF SOME VALUE
    yo: "yes"
spec:
  selector:
    matchLabels:
      app: hello
      tier: web
  template:
    metadata:
      labels:
        app: hello
        tier: web
    spec:
      containers:
      - name: hello-app
        image: gcr.io/google-samples/hello-app:2.0 # ${version} # kpt-set: hello-app:${version}
        ports:
        - containerPort: 8080
        resources:
          requests:
            cpu: 200m

```