####################################################################################

# open5gs 삭제 방법

1. namespace 삭제 : 한꺼번에 삭제 시 사용

kubectl delete namespace open5gs-ueransim

2. Mongodb 만 삭제

kubectl delete ServiceAccount mongo -n open5gs-ueransim
kubectl delete ClusterRole read-pod-service-endpoint
kubectl delete ClusterRoleBinding system:serviceaccount:open5gs-ueransim:mongo -n open5gs-ueransim
kubectl delete Service mongo -n open5gs-ueransim
kubectl delete StatefulSet mongo -n open5gs-ueransim

3. smf 만 삭제

kubectl delete svc open5gs-smf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-smf-config -n open5gs-ueransim
kubectl delete cm open5gs-smf-diameter -n open5gs-ueransim
kubectl delete StatefulSet open5gs-smf -n open5gs-ueransim

3. upf 만 삭제

kubectl delete svc open5gs-upf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-upf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-upf -n open5gs-ueransim

4. nrf 만 삭제

kubectl delete svc open5gs-nrf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-nrf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-nrf -n open5gs-ueransim

5. amf 만 삭제

kubectl delete svc open5gs-amf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-amf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-amf -n open5gs-ueransim

6. webui 만 삭제

kubectl delete svc open5gs-webui -n open5gs-ueransim
kubectl delete Deployment open5gs-webui -n open5gs-ueransim

7. ausf 만 삭제

kubectl delete svc open5gs-ausf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-ausf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-ausf -n open5gs-ueransim

8. nssf 만 삭제

kubectl delete svc open5gs-nssf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-nssf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-nssf -n open5gs-ueransim

9. udm 만 삭제

kubectl delete svc open5gs-udm-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-udm-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-udm -n open5gs-ueransim

10. udr 만 삭제

kubectl delete svc open5gs-udr-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-udr-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-udr -n open5gs-ueransim

11. bsf 만 삭제

kubectl delete svc open5gs-bsf-svc-pool -n open5gs-ueransim
kubectl delete cm open5gs-bsf-config -n open5gs-ueransim
kubectl delete StatefulSet open5gs-bsf -n open5gs-ueransim


####################################################################################

# open5gs 생성 방법

open5gs/ 에서

1. namespace 생성

kubectl create namespace open5gs-ueransim

2. Mongdb 생성

kubectl apply -f mongo/mongo-statefulset.yaml

3. nrf 생성

kubectl apply -f nrf/

또는

kubectl apply -f nrf/nrf-service.yaml
kubectl apply -f nrf/nrf-configmap.yaml
kubectl apply -f nrf/nrf-deploy.yaml

4. smf 생성

kubectl apply -f smf/

또는

kubectl apply -f smf/smf-service.yaml
kubectl apply -f smf/smf-configmap.yaml
kubectl apply -f smf/smf-free-diameter-configmap.yaml
kubectl apply -f smf/smf-deploy.yaml

5. upf 생성

kubectl apply -f upf/

또는

kubectl apply -f upf/upf-service.yaml
kubectl apply -f upf/upf-configmap.yaml
kubectl apply -f upf/upf-deploy.yaml

6. amf 생성

kubectl apply -f amf/

또는

kubectl apply -f amf/amf-service.yaml
kubectl apply -f amf/amf-configmap.yaml
kubectl apply -f amf/amf-deploy.yaml

7. webui 생성

kubectl apply -f webui/

또는

kubectl apply -f webui/webui-service.yaml
kubectl apply -f webui/webui-deploy.yaml

8. ausf 생성

kubectl apply -f ausf/

또는

kubectl apply -f ausf/ausf-service.yaml
kubectl apply -f ausf/ausf-configmap.yaml
kubectl apply -f ausf/ausf-deploy.yaml

9. nssf 생성

kubectl apply -f nssf/

또는

kubectl apply -f nssf/nssf-service.yaml
kubectl apply -f nssf/nssf-configmap.yaml
kubectl apply -f nssf/nssf-deploy.yaml

10. pcf 생성

kubectl apply -f pcf/

또는

kubectl apply -f pcf/pcf-service.yaml
kubectl apply -f pcf/pcf-configmap.yaml
kubectl apply -f pcf/pcf-deploy.yaml

11. udm 생성

kubectl apply -f udm/

또는

kubectl apply -f udm/udm-service.yaml
kubectl apply -f udm/udm-configmap.yaml
kubectl apply -f udm/udm-deploy.yaml

12. udr 생성

kubectl apply -f udr/

또는

kubectl apply -f udr/udr-service.yaml
kubectl apply -f udr/udr-configmap.yaml
kubectl apply -f udr/udr-deploy.yaml

13. bsf 생성

kubectl apply -f bsf/

또는

kubectl apply -f bsf/bsf-service.yaml
kubectl apply -f bsf/bsf-configmap.yaml
kubectl apply -f bsf/bsf-deploy.yaml

14. webui 접속

http://nodeIP주소:30000

####################################################################################
