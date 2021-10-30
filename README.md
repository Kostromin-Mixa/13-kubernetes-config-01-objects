# Домашнее задание к занятию "13.1 контейнеры, поды, deployment, statefulset, services, endpoints"   
1 задание:   
__deployment фронтенд и бекенд:__   
Находясь в папке templates коммандой kubectl apply -f my-pod.yaml создём под с двумя контейнерами.  

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
