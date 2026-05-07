University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: Cloud platforms as the basis of technology entrepreneurship     
Year: 2025/2026  
Group: U4125    
Author: Sharapova Elizaveta Igorevna  
Lab: Lab3  
Date of create: 05.04.2026  
Date of finished:

# Лабораторная работа №3
## "Исследование Cloud Storage"    
**Цель работы:**  
познакомиться с основными понятиями и принципами работы облачного хранилища, изучить различные модели хранения данных (блок, файл, объектное хранилище), познакомиться с основными сервисами и функционалом, предоставляемыми облачными хранилищами

---

### Ход работы 
**1. Создание Cloud Storage bucket:**  
Во вкладке `Cloud Storage -> Buckets` был создан бакет с именем `esharapova-bucket-lab3`.   
![3-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab3%20(3-1).png)

**2. Загрузка изображений в Cloud Storage bucket:**  
Через вкладку `Upload` в созданный бакет были загружены три графических файла в формате `.png`.    
![3-2](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab3%20(3-2).png)

**3. Создание новой папки и перемещение туда файлов:**  
Внутри созданного бакета была сформирована папка `France`.    
С помощью функции `Move object` все три файла были перемещены в новую папку.    
В качестве целевого пути было указано `esharapova-bucket-lab3/France/`.    
![3-3](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab3%20(3-3).png)
![3-4](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab3%20(3-4).png)  

После завершения операции все три файла успешно переместились в папку `France`.    
![3-5](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab3%20(3-5).png)

**4. Настройка публичного доступа:**  
Для настройки публичного доступа были выбраны следующие показатели:    
- Пользователи: `allUsers`   
- Роль: `Storage Object Viewer`   
Благодаря этой настройке любой пользователь в интернете получил возможность читать объекты бакета   
![3-6](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/c950d760804caebf54f0395ae928c1c302b4503d/lab3/lab%20(3-6).png)

**5. Создание публичной ссылки:**  
Через контекстное меню была скопирована общедоступная ссылка:   
Кроме того в верхней части интерфейса бакета публичный доступ из статуса `Not public` перешел на `Access granted to public principals`.  
![3-7 НАДО ВСТАВИТЬ]()

**6. Тестирование публичной ссылки:**  
Скопированная ссылка была успешно открыта в браузерном окне, а изображение отобразилось корректно, что говорит об исправной работе публичного доступа.  
![3-8 НАДО ВСТАВИТЬ]()

**7. Очистка ресурсов:**  
По окончании работы и находившиеся в нём файлы были удалены.   

### Результаты лабораторной работы  
В результате данной работы:    
- создан бакет в облачном хранилище  
- загружены изображения, создана новая папка и выполнено перемещение файлов  
- настроен публичный доступ и сгенерированы общедоступные ссылки  
- написан отчет по проделанной работе с описанием выполненных задач и скриншотами   
