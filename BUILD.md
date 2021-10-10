 git add .
 git commit -m "Versao inicial completa"
 git push
 npm run build
 podman build -t webcv:0.3 .
 podman tag webcv:0.3 iberejr/webcv:latest
 podman push iberejr/webcv:latest
 kubectl delete pod -l app=webcv

