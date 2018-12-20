https://istio.io/docs/tasks/traffic-management/request-timeouts/

# Setting request timeout
```bash
kubectl apply -f samples/bookinfo/networking/virtual-service-all-v1.yaml
```

# Route all to v2
```bash
cat <<EOF | kubectl apply -f -
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: reviews
spec:
  hosts:
    - reviews
  http:
  - route:
    - destination:
        host: reviews
        subset: v2
EOF
```

# Add 2s delay
```bash
cat <<EOF | kubectl apply -f -
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: ratings
spec:
  hosts:
  - ratings
  http:
  - fault:
      delay:
        percent: 100
        fixedDelay: 2s
    route:
    - destination:
        host: ratings
        subset: v1
EOF
```

# See 2s delay for rating

# Add 1s timeout (default 15s)
```bash
cat <<EOF | kubectl apply -f -
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: reviews
spec:
  hosts:
  - reviews
  http:
  - route:
    - destination:
        host: reviews
        subset: v2
    timeout: 0.5s
EOF
```

# See 1s delay but no reviews available

# Cleanup
```bash
kubectl delete -f samples/bookinfo/networking/virtual-service-all-v1.yaml
```