**1.- Iniciar el cluster con el siguiente comando**
kubectl apply -f deployment.yml

**2.- Verificar el despliegue**
kubectl get all

    pod/passwordapi-b6f77cdf9-lqvdf   1/1     Running   0          38s

    NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
    service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   4d22h

    NAME                          READY   UP-TO-DATE   AVAILABLE   AGE
    deployment.apps/passwordapi   1/1     1            1           38s

    NAME                                    DESIRED   CURRENT   READY   AGE
    replicaset.apps/passwordapi-b6f77cdf9   1         1         1       38s

**3.- Acceder al pod y ejecutar el bash**
kubectl exec -it pod/passwordapi-b6f77cdf9-lqvdf --  bash

**4.- Hacer CURL desde el bash**
PS C:\docker\ejercicio_11\deployment> kubectl exec -it pod/passwordapi-b6f77cdf9-lqvdf --  bash

    root@passwordapi-b6f77cdf9-lqvdf:/usr/src/app# curl localhost:3000/password
    {"password":"!601CcRrRrEe"}root@passwordapi-b6f77cdf9-lqvdf:/usr/src/app# 

**5.- Eliminar el deploy realizado.**
PS C:\docker\ejercicio_11\deployment> kubectl delete deployment.apps/passwordapi
deployment.apps "passwordapi" deleted
