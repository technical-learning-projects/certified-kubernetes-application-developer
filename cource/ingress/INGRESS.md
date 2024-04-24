As we already discussed **Ingress** in our previous lecture. Here is an update.

In this article, we will see what changes have been made in previous and current versions in **Ingress**.

Like in `apiVersion`, `serviceName` and `servicePort` etc.

![Diagram](https://img-c.udemycdn.com/redactor/raw/article_lecture/2021-08-17_16-08-15-344e2f95e7ebee44be33e8b5f78acacb.png)

Now, in k8s version **1.20+** we can create an Ingress resource from the imperative way like this:

Format:

```shell
kubectl create ingress <ingress-name> --rule="host/path=service:port"
```

Example:

```shell
kubectl create ingress ingress-test --rule="wear.my-online-store.com/wear*=wear-service:80"
```

Find more information and examples in the below reference link:  
https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-em-ingress-em-

References:

https://kubernetes.io/docs/concepts/services-networking/ingress

https://kubernetes.io/docs/concepts/services-networking/ingress/#path-types

### FAQ - What is the rewrite-target option?

Different ingress controllers have different options that can be used to customise the way it works. NGINX Ingress
controller has many options that can be seen [here](https://kubernetes.github.io/ingress-nginx/examples/). I would like to explain one such option that we will use in our labs.
The [Rewrite](https://kubernetes.github.io/ingress-nginx/examples/rewrite/) target option.

Our `watch` app displays the video streaming webpage at `http://<watch-service>:<port>/`

Our `wear` app displays the apparel webpage at `http://<wear-service>:<port>/`

We must configure Ingress to achieve the below. When user visits the URL on the left, his request should be forwarded
internally to the URL on the right. Note that the /watch and /wear URL path are what we configure on the ingress
controller, so we can forward users to the appropriate application in the backend. The applications don't have this
URL/Path configured on them:

`http://<ingress-service>:<ingress-port>/watch` --> `http://<watch-service>:<port>/`

`http://<ingress-service>:<ingress-port>/wear` --> `http://<wear-service>:<port>/`

Without the `rewrite-target` option, this is what would happen:

`http://<ingress-service>:<ingress-port>/watch` --> `http://<watch-service>:<port>/watch`

`http://<ingress-service>:<ingress-port>/wear` --> `http://<wear-service>:<port>/wear`

Notice `watch` and `wear` at the end of the target URLs. The target applications are not configured with `/watch` or `/wear`
paths. They are different applications built specifically for their purpose, so they don't expect `/watch` or `/wear` in the
URLs. And as such the requests would fail and throw a `404` not found error.

To fix that we want to "ReWrite" the URL when the request is passed on to the watch or wear applications. We don't want
to pass in the same path that user typed in. So we specify the `rewrite-target` option. This rewrites the URL by replacing
whatever is under `rules->http->paths->path` which happens to be `/pay` in this case with the value in `rewrite-target`. This
works just like a search and replace function.

For example: `replace(path, rewrite-target)`  
In our case: `replace("/path","/")`
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: test-ingress
  namespace: critical-space
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
    - http:
        paths:
          - path: /pay
            pathType: Prefix
            backend:
              service:
                name: pay-service
                port:
                  number: 8282
```
In another example given [here](https://kubernetes.github.io/ingress-nginx/examples/rewrite/), this could also be:

`replace("/something(/|$)(.*)", "/$2")`
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /$2
  name: rewrite
  namespace: default
spec:
  rules:
    - host: rewrite.bar.com
      http:
        paths:
          - path: /something(/|$)(.*)
            pathType: Prefix
            backend:
              service:
                name: http-svc
                port:
                  number: 80     
```


