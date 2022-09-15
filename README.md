## This is a demo custom catalog repo for DKP 2.1.1 +

To add this to a project simply create a gitrepository resource as shown below to the given project

```
export PROJECT=flixdemo

kubectl apply -f - <<EOF
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: GitRepository
metadata:
  name: flix-catalog-repo
  namespace: ${PROJECT}
  labels:
    kommander.d2iq.io/gitapps-gitrepository-type: catalog
    kommander.d2iq.io/gitrepository-type: catalog
spec:
  interval: 1m0s
  ref:
    branch: master
  timeout: 20s
  url: https://github.com/phenderson-d2iq/kommander-catalog
EOF

``` 

Here is a screenshot of the custom catalogs in the DKP Dashboard

![Kommander Portal With Custom Catalog Item](./image.png)

