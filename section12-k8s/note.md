- Imperatively 
- Declaratively 
- API references: https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.24/#deployment-v1-apps

# Deployment
- **images need to push in docker hub**
- `docker build -t kub-frist-app . `
- `docker tag kub-frist-app lamnt67/kub-first-app `
- `docker push lamnt67/kub-first-app`
- `kubectl create deployment first-app --image=lamnt67/kub-first-app`

# Services
- `kubectl expose deployment first-app --type=LoadBalancer --port=8080 `
- `minikube service first-app`

# Update the image
- Build new image: `docker build -t lamnt67/kub-first-app:2 .`
- Push to registry: `docker push lamnt67/kub-first-app:2`
- Set new image for deployment: `kubectl set image deployment/first-app kub-first-app=lamnt67/kub-first-app:2`
- Check update history: `kubectl rollout status deployment/first-app`

- Update 1 images doesn't exit: ` kubectl set image deployment/first-app kub-first-app=lamnt67/kub-first-app:3`
- Check rollout status: `kubectl rollout status deployment/first-app`
- In dashboad, we can see one pod fall, but another pod is running (Thanks for the deployment stragery) but we can't update (because non-exit image)
- Rollback to the previous deployment: `kubectl rollout undo deployment/first-app `
- Check history rollout: `kubectl rollout history deployment/first-app`
- Check detail: ` kubectl rollout history deployment/first-app --revision=3`
- Rollback to specific revision: `kubectl rollout undo deployment/first-app --to-revision=1` 