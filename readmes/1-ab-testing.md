https://istio.io/docs/tasks/traffic-management/request-routing/

# Enable default route
```bash
cat samples/bookinfo/networking/virtual-service-all-v1.yaml
kubectl apply -f samples/bookinfo/networking/virtual-service-all-v1.yaml
kubectl get virtualservices -o yaml
```

# See that there is only one version routed
```bash
kubectl get destinationrules -o yaml
```

# User-based testing (A/B testing)
```bash
cat samples/bookinfo/networking/virtual-service-reviews-test-v2.yaml
kubectl apply -f samples/bookinfo/networking/virtual-service-reviews-test-v2.yaml
kubectl get virtualservice reviews -o yaml
```

# Connect with Jason on productpage

# Cleanup
```bash
kubectl delete -f samples/bookinfo/networking/virtual-service-all-v1.yaml
```