# Kubernetes deployment

OWASP Juice Shop is intentionally insecure and should be used only in an isolated
training environment.

These manifests require an Ingress NGINX controller and a `ReadWriteOnce`
StorageClass.

Deploy with:

```sh
kubectl apply -k kubernetes
```

The app is exposed at `http://juice-shop.local` after the host is mapped to the
Ingress address. To use port-forwarding instead:

```sh
kubectl -n juice-shop port-forward service/juice-shop 3000:80
```

Then open `http://localhost:3000`.

To remove the deployment and persistent data:

```sh
kubectl delete -k kubernetes
kubectl delete pvc -n juice-shop juice-shop-data
```
