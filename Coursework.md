# Курсовая работа по итогам модуля "DevOps и системное администрирование"

Курсовая работа необходима для проверки практических навыков, полученных в ходе прохождения курса "DevOps и системное администрирование".

Мы создадим и настроим виртуальное рабочее место. Позже вы сможете использовать эту систему для выполнения домашних заданий по курсу

## Задание

1. Создайте виртуальную машину Linux.
![IMG](/images/Task_1.jpg)
2. Установите ufw и разрешите к этой машине сессии на порты 22 и 443, при этом трафик на интерфейсе localhost (lo) должен ходить свободно на все порты.
![IMG](/images/Task_2_ufw.jpg)
![IMG](/images/Task_2_ports_22_and_443.jpg)
![IMG](/images/Task_2_Localhost.jpg)
3. Установите hashicorp vault ([инструкция по ссылке](https://learn.hashicorp.com/tutorials/vault/getting-started-install?in=vault/getting-started#install-vault)).
![IMG](/images/Task_3.jpg)
4. Cоздайте центр сертификации по инструкции ([ссылка](https://learn.hashicorp.com/tutorials/vault/pki-engine?in=vault/secrets-management)) и выпустите сертификат для использования его в настройке веб-сервера nginx (срок жизни сертификата - месяц)..
![IMG](/images/Task_4_install_jq.jpg)  
![IMG](/images/Task_4_Certificates.jpg)  
5. Установите корневой сертификат созданного центра сертификации в доверенные в хостовой системе. 
###### скопировал ключ в папку вагрант, чтобы мог отработать с ним на хосте.  
![IMG](/images/Task_5_1.jpg)  
###### Далее непосредственно установка корневого сертификата в доверенные в хостовой системе.  
![IMG](/images/Task_5_2.jpg)  
![IMG](/images/Task_5_3.jpg)  
![IMG](/images/Task_5_4.jpg)  
![IMG](/images/Task_5_5.jpg)  
![IMG](/images/Task_5_6.jpg)  
![IMG](/images/Task_5_7.jpg)  
6. Установите nginx.  
![IMG](/images/Task_6_Install_nginx.jpg)
7. По инструкции ([ссылка](https://nginx.org/en/docs/http/configuring_https_servers.html)) настройте nginx на https, используя ранее подготовленный сертификат:
  - можно использовать стандартную стартовую страницу nginx для демонстрации работы сервера;
  - можно использовать и другой html файл, сделанный вами;   
![IMG](/images/Task_7.jpg)
###### подскажите пожалуйста, правильно ли настроил? и у меня при запуске команды systemctl restart nginx происходит запрос пароля. Какой там пароль? можете подсказать пожалуйста.   
![IMG](/images/Task_7_2.jpg)    
###### При использовании команд sudo systemctl restart nginx и sudo -i сразу пишет что error code. При команде systemctl restart nginx требует пароль, написал vagrant - вышла команда AUTHENTICATION COMPLETE. Где может быть проблема подскажите пожалуйста.
8. Откройте в браузере на хосте https адрес страницы, которую обслуживает сервер nginx.
9. Создайте скрипт, который будет генерировать новый сертификат в vault:
  - генерируем новый сертификат так, чтобы не переписывать конфиг nginx;
  - перезапускаем nginx для применения нового сертификата.
10. Поместите скрипт в crontab, чтобы сертификат обновлялся какого-то числа каждого месяца в удобное для вас время.

## Результат

Результатом курсовой работы должны быть снимки экрана или текст:

- Процесс установки и настройки ufw
- Процесс установки и выпуска сертификата с помощью hashicorp vault
- Процесс установки и настройки сервера nginx
- Страница сервера nginx в браузере хоста не содержит предупреждений 
- Скрипт генерации нового сертификата работает (сертификат сервера ngnix должен быть "зеленым")
- Crontab работает (выберите число и время так, чтобы показать что crontab запускается и делает что надо)

## Как сдавать курсовую работу

Курсовую работу выполните в файле readme.md в github репозитории. В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.

Также вы можете выполнить задание в [Google Docs](https://docs.google.com/document/u/0/?tgif=d) и отправить в личном кабинете на проверку ссылку на ваш документ.
Если необходимо прикрепить дополнительные ссылки, просто добавьте их в свой Google Docs.

Перед тем как выслать ссылку, убедитесь, что ее содержимое не является приватным (открыто на комментирование всем, у кого есть ссылка), иначе преподаватель не сможет проверить работу. 
Ссылка на инструкцию [Как предоставить доступ к файлам и папкам на Google Диске](https://support.google.com/docs/answer/2494822?hl=ru&co=GENIE.Platform%3DDesktop).