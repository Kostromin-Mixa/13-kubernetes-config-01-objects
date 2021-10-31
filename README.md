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
![deploy](https://user-images.githubusercontent.com/78191008/139575304-6903af07-6229-46c5-a5ed-32ff6705621e.png)   

Этим конфигурационным файлом создём POD БД Postgre через statefulset   
[db-pod.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/db-pod.yaml)   
![sts](https://user-images.githubusercontent.com/78191008/139575300-d5453b56-2f1f-4d7e-8260-efbb944384dd.png)   

Все PODs запущены   
![pods](https://user-images.githubusercontent.com/78191008/139575296-66d7f832-2278-42cf-82df-2898cc304aa7.png)   

Создаём сервысы:   
[front-services.yaml](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/service-front.yaml)   
[back-services](https://github.com/Kostromin-Mixa/13-kubernetes-config-01-objects/blob/main/service-back.yaml)   
Все сервисы запущены:   

![svc](https://user-images.githubusercontent.com/78191008/139575309-ebd54a15-b3ca-45e4-96e2-8c4c25deac93.png)

