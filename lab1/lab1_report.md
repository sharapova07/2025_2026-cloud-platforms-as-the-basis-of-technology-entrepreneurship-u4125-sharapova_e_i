University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: Cloud platforms as the basis of technology entrepreneurship     
Year: 2025/2026  
Group: U4125    
Author: Sharapova Elizaveta Igorevna  
Lab: Lab1  
Date of create: 04.04.2026  
Date of finished:

# Лабораторная работа №1
## "Обзор Google Cloud и исследование основных сервисов"    
**Цель работы:**  
познакомиться с основными возможностями и преимуществами облачной платформы Google Cloud  

---

### Ход работы 
**1. Создание Service Account:**  
Создан сервисный аккаунт с ролью `Storage Admin` и именем `esharapova-sa-lab1`  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab1%20(1-1).png) 
![1-2](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab1%20(1-2).png) 
**2. Создание виртуальной машины:**   
Создана виртуальная машина с именем `esharapova-vm-lab1` и параметрами:  
- Machine type: e2-micro (тип виртуальной машины из семейства e2)  
- Provisioning model: Spot (модель предоставления ресурсов - прерываемая)  
![1-3](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-3).png)
![1-4](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-4).png) 
**3. Подключение к виртуальный машине и работа с Cloud Storage:**
- Через SSH было произведено подключение к VM
- При помощи утилиты `gcloud` найдены бакет `lab1-bucket-itmo` и скопированы 3 файла в локальную папку `lab1-files`
- Благодаря команде `ls -lah` было отражено, что эти файлы хранятся у меня на VM
Таким образом, все три файла были успешно скачены
```
mkdir ~/lab1-files 
cd ~/lab1-files 
gcloud storage cp gs://lab1-bucket-itmo/* . 
ls -lah 
```
![1-5](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-5).png) 
![1-6](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-6).png) 
**4. Смена роли на Compute Viewer:**  
В сервисом аккаунте изменены права доступа со `Storage Admin` на `Compute Viewer`
![1-7](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-7).png) 
![1-8](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/8609ee0f82477774391ece634e6fdfdd19f9374f/lab1/lab%20(1-8).png) 

**5. Копирование данных с новой ролью:**  
В терминале VM была повторно выполнена команда копирования, которая завершилась ошибкой 403:  
```
cd ~/lab1-files
gcloud storage cp gs://lab1-bucket-itmo/* .
```
**Таким образом:**   
при попытке копирования файлов с доступом `Compute Viewer` была выдана ошибка 403, поскольку данная роль предоставляет права только на просмотр информации о VM. В то время как `Storage Admin` предоставляет полный контроль над ресурсами Cloud Storage, позволяя управлять объектами и бакетами, что мы и увидели в ходе выполнения данной лабораторной работы.

### Результаты лабораторной работы  
В результате данной работы:    
- создан Service Account с ролью Storage Admin  
- создана VM e2-micro в режиме Spot  
- скопированы файлы из бакета на VM   
- роль Service Account изменена на Compute Viewer (повторное копирование вызвало ошибку 403 Access Denied)  
- написан отчет по проделанной работе с описанием выполненных задач и скриншотами  
