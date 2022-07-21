# Lab Description
- Create nfs server using nfs image 
- Mount pod with nfs server to write data 

# Steps 
- Create services to expose nfs server to pods inside the cluster 
- Create nfs-server pod 
- Create pod mounting to nfs-server 
- Check that the NFS volume works:
 `kubectl exec -it pod-using-nfs sh`
 `kubectl exec -it nfs-server-pod sh`
