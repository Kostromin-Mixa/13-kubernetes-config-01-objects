# Домашнее задание к занятию "13.1 контейнеры, поды, deployment, statefulset, services, endpoints"   
## __1 задание:__   
__deployment фронтенд и бекенд:__   
Находясь в папке templates коммандой kubectl apply -f my-pod.yaml создём под с двумя контейнерами.  
[front-back-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/front-back-pod.yaml)   
apiVersion: apps/v1   
kind: Deployment   
metadata:   
  labels:   
    app: multitool   
  name: front-back   
  namespace: default  
spec:   
  replicas: 1   
  selector:   
    matchLabels:   
      app: multitool   
  template:   
    metadata:   
      labels:   
        app: multitool   
    spec:   
      containers:   
      - image: nginx:1.20   
        imagePullPolicy: IfNotPresent   
        name: frontend   
      - image: praqma/network-multitool:alpine-extra   
        imagePullPolicy: IfNotPresent   
        name: backend   
        env:   
          - name: HTTP_PORT   
            value: "8080"      

__база данных — через statefulset:__   
[db-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/db-pod.yaml)   
apiVersion: apps/v1   
kind: StatefulSet   
metadata:   
  name: postgresql-db   
spec:   
  serviceName: postgresql-db-service   
  selector:   
    matchLabels:   
      app: postgresql-db   
  replicas: 1   
  template:   
    metadata:   
      labels:   
        app: postgresql-db   
    spec:   
      containers:   
        - name: postgresql-db   
          image: postgres:latest   
          volumeMounts:   
            - name: postgresql-db-disk   
              mountPath: /data   
          env:   
            - name: POSTGRES_PASSWORD   
              value: test   
            - name: PGDATA   
              value: /data/pgdata   
   volumeClaimTemplates:   
    - metadata:   
        name: postgresql-db-disk   
      spec:   
        accessModes: ["ReadWriteOnce"]   
        resources:   
          requests:   
            storage: 25Gi   


## __2 задание:__   





![pods](https://user-images.githubusercontent.com/78191008/139575296-66d7f832-2278-42cf-82df-2898cc304aa7.png)

![sts](https://user-images.githubusercontent.com/78191008/139575300-d5453b56-2f1f-4d7e-8260-efbb944384dd.png)

![deploy](https://user-images.githubusercontent.com/78191008/139575304-6903af07-6229-46c5-a5ed-32ff6705621e.png)

![svc](https://user-images.githubusercontent.com/78191008/139575309-ebd54a15-b3ca-45e4-96e2-8c4c25deac93.png)

