Elkészítettem a házifeladatot, egyelőre csak Kustomize-al, kérem nézd meg, és ha jó, megyek rá a Helm -es megoldásra is.

Kiadott parancsok:

Elszeparált névterek kreálása:

kubectl create namespace hw4-test
kubectl create namespace hw4-dev
kubectl create namespace hw4-prod

Podok létrehozása:

kubectl apply -k overlays/prod
kubectl apply -k overlays/test
kubectl apply -k overlays/dev
