# iks-strongswan

## startup procedure minikube

minikube start --nodes=3 --memory=8192 --cpus=4 --disk-size=20g --driver=docker \
kubectl apply -f deployment.yaml \
kubectl exec -it ipsec-client-<pod-id> -c strongswan -- /usr/sbin/swanctl --load-all \
kubectl exec -it ipsec-server-<pod-id> -c strongswan -- /usr/sbin/swanctl --load-all \
kubectl exec -it ipsec-client-<pod-id> -c strongswan -- /usr/sbin/swanctl --initiate --ike client-tunnel \


## startup procedure VM

sudo systemctl enable strongswan-starter
sudo systemctl start strongswan-starter
sudo systemctl status strongswan-starter