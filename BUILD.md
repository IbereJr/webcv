VERSION=$( echo $VERSION + 0.1 | bc )
git add .
git commit -m "Versao inicial completa"
git push
npm run build
podman build -t webcv:${VERSION} .
podman tag webcv:${VERSION} iberejr/webcv:latest
podman push iberejr/webcv:latest
kubectl delete pod -l app=webcv

