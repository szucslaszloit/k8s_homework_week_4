Elkészítettem a házifeladatot, egyelőre csak Kustomize-al, kérem nézd meg, és ha jó, megyek rá a Helm -es megoldásra is.

A Deploymentet, és a Sevice YAML-öket egy-egy fájlba tettem: /base/frontapp.yaml és /base/backapp.yaml
(Nem vettem külön külön őket.)

Prodból beenged a http://application.cubix.localhost:8080/frontapp
Testből beenged a http://other.cubix.localhost:8080/frontapp
Devből egyik sem enged be.

Kiadott parancsok:

Elszeparált névterek kreálása:

kubectl create namespace hw4-test

kubectl create namespace hw4-dev

kubectl create namespace hw4-prod


Podok létrehozása:

kubectl apply -k overlays/prod

kubectl apply -k overlays/test

kubectl apply -k overlays/dev

Podok listázása:

kubectl get pods -n hw4-test

kubectl get pods -n hw4-prod

kubectl get pods -n hw4-dev

Logok kiíratása:

kubectl logs frontapp-pod-neve -n hw4-test

kubectl logs backapp-pod-neve -n hw4-test

kubectl logs frontapp-pod-neve -n hw4-dev

kubectl logs backapp-pod-neve -n hw4-dev

kubectl logs frontapp-pod-neve -n hw4-prod

kubectl logs backapp-pod-neve -n hw4-prod

Erőforrások törlése:

kubectl delete -k overlays/prod

kubectl delete -k overlays/test

kubectl delete -k overlays/dev

Helm-es parancsok:

helm install My-App -f test-values.yaml . -n hw4-test

helm install My-App -f prod-values.yaml . -n hw4-prod

helm install My-App -f test-values.yaml . -n dev-test

Címkék szerinti lekérdezés:

kubectl get all -l homework=backapp -n hw4-test

kubectl get all -l homework=frontapp -n hw4-test


kubectl get all -l homework=backapp -n hw4-prod

kubectl get all -l homework=frontapp -n hw4-prod

kubectl get all -l homework=backapp -n hw4-dev

kubectl get all -l homework=frontapp -n hw4-dev



