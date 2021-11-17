# Домашнее задание к занятию "13.1 контейнеры, поды, deployment, statefulset, services, endpoints"   
## __1 задание:__   
__deployment фронтенд и бекенд:__   
Этим конфигурационным файлом создём POD с двумя контейнерами, frontend и backend.  
[front-back-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/front-back-pod.yaml)   

__база данных — через statefulset:__   
[db-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/db-pod.yaml)   

## __2 задание:__   
Этим конфигурационным файлом создём POD через deployment   
[front-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/front-pod.yaml)   
[back-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/back-pod.yaml)   

Этим конфигурационным файлом создём POD БД Postgre через statefulset   
[db-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/db-pod.yaml)   

Создаём сервысы:   
[front-services.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/service-front.yaml)   
[back-services.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/service-back.yaml)   

Проверяем, что всё запущено:   

![all](https://user-images.githubusercontent.com/78191008/139811376-e6819c9d-be37-4998-9bba-d67b8099b135.png)
![2021-11-02_13-28-37](https://user-images.githubusercontent.com/78191008/139811513-dd015bfd-b152-4a34-96e8-5cb874743d38.png)
