# argocd-app-config

#### Commands

```bash
# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

# you can change and delete init password

# git clone https://github.com/georg480/argocd-app-config.git
# cd argocd-app-config/
# kubectl apply -f application.yaml
# nur Änderungen von github runter laden
# git push

GIT-Befehle
git init
Im aktuellen Ordner (Auswahl in der Konsole) wird ein GIT-Ordner eingerichtet.
git clone <Link zu Repository>
Im aktuellen Ordner werden alle Dateien aus der GIT-Ablage hineinkopiert.
git status
Zeigt an, welche Dateien verändert und noch nicht abgeglichen wurden.
git add . 
Fügt alle Dateien in die commit-Zwischenablage ein.
git commit -m "Nachricht"
Speichert alle Änderungen mit einer persönlichen Nachricht.
Hier empfiehlt es sich, zu Beginn eine Versionsnummer anzugeben.
git pull <Branch>
Holt alle Änderungen von der Ablage (Repository) und passt die eigenen Dateien entsprechend an.
git push <Branch>
Alle neuen Commits werden zur Ablage (Repository) hochgeladen.
git revert
Setzt den aktuellen Branch auf einen bestimmten Commit (Version) zurück.
git reset
ACHTUNG: Dieser Befehl kann zu Komplikationen in der Ablage führen und sollte nur vom 
Projektleiter durchgeführt werden.
Setzt alle Änderungen eines Commits zurück. Der Commit kann auch komplett entfernt werden
 
```
</br>

#### Links

* Config repo: [https://gitlab.com/nanuchi/argocd-app-config](https://gitlab.com/nanuchi/argocd-app-config)

* Docker repo: [https://hub.docker.com/repository/docker/nanajanashia/argocd-app](https://hub.docker.com/repository/docker/nanajanashia/argocd-app)

* Install ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

* Login to ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)

* ArgoCD Configuration: [https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)
