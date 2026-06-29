# iks-strongswan

## startup procedure

minikube start
kubectl apply -f deployment.yaml
kubectl exec -it ipsec-server-<pod-id> -c strongswan -- /usr/sbin/swanctl --load-all
kubectl exec -it ipsec-client-<pod-id> -c strongswan -- /usr/sbin/swanctl --load-all
kubectl exec -it ipsec-client-<pod-id> -c strongswan -- /usr/sbin/swanctl --initiate --ike client-tunnel