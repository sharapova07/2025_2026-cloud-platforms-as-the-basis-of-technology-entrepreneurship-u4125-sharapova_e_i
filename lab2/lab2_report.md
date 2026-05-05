University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: Cloud platforms as the basis of technology entrepreneurship     
Year: 2025/2026  
Group: U4125    
Author: Sharapova Elizaveta Igorevna  
Lab: Lab2 
Date of create: 04.04.2026  
Date of finished:

# Лабораторная работа №2  
## "Исследование Cloud Run"    
**Цель работы:**  
познакомиться с работой Cloud Run

---

### Ход работы 
**1. Создание Cloud Run:**  
Создан сервис в Cloud Run на основе образа контейнера `us-docker.pkg.dev/cloudrun/container/hello` и с именем `esharapova-hello-lab2`  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-1).png)
**2. Тестирование сервиса:**    
После создания сервиса этапы Creating service, Creating revision и Routing traffic перешли в статус Completed.    
Также при переходе по ссылке, предоставленной Cloud Run, сервис выдал приветственное сообщение "It's running!", что означающает его исправную работу.  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-2).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab%20(2-3).png )
**3. Анализирование метрик сервиса:**  
В ходе работы были проанализированы следующие метрики:
1. Request count (активность сервиса в течение дня)     
2. Request latencies (задержки обработки):  
- 50% запросов выполнялись около 5ms    
- 95% запросов: 9ms   
- 99% запросов: 10ms  
3. End-to-end latency (полное время ожидания пользователя) оказалось выше из-за сетевых задержек:  
- 50%: 28ms 
- 95%: 33ms 
- 99%: 34ms   
В результате метрики показывают, что сервис работает быстро и стабильно  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-4).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-5).png)

**4. Анализирование логов сервиса:**  
В логах зафиксированы HTTP-запросы к сервису. Все запросы завершились успешно с кодом 200. Время обработки составило от 2 до 9 миллисекунд, что говорит о быстрой работе сервиса.  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-6).png)

**5. Изменение конфигурации:**  
Через вкладку Edit & deploy new revision был изменен порт контейнера с 8080 на 8090.  
В результате, сервис работает без ошибок и контейнер запустился штатно. Все потому, что Cloud Run сам подстраивается: у него есть встроенная переменная PORT, и контейнер автоматически начинает слушать тот порт, который ему укажут.  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-7).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-8).png)

**6. Переключение трафика между версиями:**  
Через вкладку Manage traffic было настроено равномерное распределение трафика. В итоге: 
- Обе ревизии успешно обрабатывают поступающие запросы  
- Доступность сервиса сохраняется на 100%  
- Ошибки при обработке запросов отсутствуют  
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-9).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-10).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-11).png)
![1-1](https://github.com/sharapova07/2025_2026-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-sharapova_e_i/blob/47e54861a95d396b9ba21ed572eacadf822acdae/lab2/lab2%20(2-12).png)

### Результаты лабораторной работы  
В результате данной работы:    
- создан Cloud Run сервис из образа `us-docker.pkg.dev/cloudrun/container/hello` с минимальными ресурсами    
- выполнен анализ метрик и логов  
- произведена смена порта на 8090  
- выполнено управление трафиком между ревизиями: 50/50%    
- написан отчет по проделанной работе с описанием выполненных задач и скриншотами  
