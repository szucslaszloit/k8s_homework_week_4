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





