- **Sate** is data createdd and used by your application which must not be lost 
  - User generated data, user account (often sotred in DB, but could also be files)
  - Imtermediate results derived by the app (often stored in memory, temporary DB tables or files)

- K8s can mount Volumes into Containers: 
  - A broad variety of Volume types: 
    - Local Volumes 
    - Cloud-provider 
- Persistance volume as a resouce in k8s's cluster

# Lab 
- create deployment and service
- Get the LB of the replicas set 
- Use postman to test request:
  - **POST** json data 
  - Check with **GET**
- 