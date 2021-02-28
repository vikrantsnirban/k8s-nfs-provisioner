# nfs-provisioner

# Steps
1. Load tar file to Docker:  docker load < nfs-provisioner.tar
2. Tag Docker image to your Docker Repository: docker tag quay.io/external_storage/nfs-client-provisioner:v3.1.0-k8s1.11 vikrantsnirban/nfs-client-provisioner:v3.1.0-k8s1.11
3. Push to Docker Repository: docker push vikrantsnirban/nfs-client-provisioner:v3.1.0-k8s1.11
4. deploy nfs provisioner: kubectl apply -f nfs-provisioner.yaml (ICE: kubectl replace -f sc.yaml --force)
5. Verify nfs provisioner deployment: kubectl get deployment,sc
6. Test Provisioner by deploying statefulset: kubectl apply -f greetings-statefulset.yaml
7. Verify PV and PVC: kubectl get pv,pvc


