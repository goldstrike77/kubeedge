# Deploy the cloud part into a k8s cluster.
kubectl apply -f crds/devices
kubectl apply -f crds/reliablesyncs
kubectl apply -f crds/router
kubectl apply -f cloud

# generate the tls certs.
sudo tools/certgen.sh buildSecret | tee cloud/06-secret.yaml
