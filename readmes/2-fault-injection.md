https://istio.io/docs/tasks/traffic-management/fault-injection/

# Inject HTTP delay
```bash
kubectl apply -f samples/bookinfo/networking/virtual-service-all-v1.yaml
kubectl apply -f samples/bookinfo/networking/virtual-service-reviews-test-v2.yaml
cat samples/bookinfo/networking/virtual-service-ratings-test-delay.yaml
kubectl apply -f samples/bookinfo/networking/virtual-service-ratings-test-delay.yaml
kubectl get virtualservice ratings -o yaml
```

# Login with Jason and see 7s delay

# Fix the delay to 3s

# Login with another user to see that only Jason is affected

# Inject HTTP abort
```bash
cat samples/bookinfo/networking/virtual-service-ratings-test-abort.yaml
kubectl apply -f samples/bookinfo/networking/virtual-service-ratings-test-abort.yaml
kubectl get virtualservice ratings -o yaml
```

# Login with Jason and see "product ratings not available"

# Cleanup
```bash
kubectl delete -f samples/bookinfo/networking/virtual-service-all-v1.yaml
```