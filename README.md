# DOCKER


### Установка Docker:

1. поднять сервер (например Ubuntu на виртуальной машине)
```
cat /etc/os-release - посмотреть версию Ubuntu
```
2. sudo apt update
3. sudo apt install apt-transport-https
4. `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
5. `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`
6. sudo apt update
7. sudo apt install docker-latest (latest - версия)
8. sudo systemctl status docker - проверить, что docker активен
9. docker -v - версия docker
10. sudo usermod -aG docker $USER (надо будет сделать exit и снова запустить) - добавить пользователя в группу docker, чтобы не приходилось постоянно писать sudo (у меня не сработало)


### Команды DOCKER
1. __sudo docker run hello-world__ - запуск image с название hello-world - используется для тестов 


2. __sudo docker ps__ - посмотреть запущенные контейнеры, в т.ч. id контейнера, который используется для запуска или остановки



3. __sudo docker ps -a__ - посмотреть все существовавщие контейнеры



4. __sudo docker images__ - посмотреть существующие images



5. __sudo docker run -p 80:80 -d nginx__ - запустить контейнер nginx на 80 порт (-d - deamon значит, что в терминале выведет полный id контейнера и отдаст командную строку), после этого начальная страница nginx отразится в браузере по адресу localhost:80



6. __sudo docker run -p 80:80 -it nginx__ - (-it - не отдаст командную строку, пока не завершить процесс Ctrl + C)


7. __sudo docker stop [container id]__ - (container id брать изкоманды sudo docker ps) - останавливает контейнер


8. __sudo docker restart [container id]__ - перезапустить контейнер


9. __docker run -d [image_id|repository]__ - запустить image


10. __docker inspect [container_id|container_name]__ - просмотреть информацию о контейнере (в т.ч. IP-адрес контейнера)


11. __sudo docker search tomcat__ - поиск image по имени tomcat (выдаст список с похожими именами)

12. docker pull tomcat - скачать image tomcat без запуска

13. __sudo rmi [image name | image id]__ - удалить image

14. __docker rm [container id]__ - удалить контейнер

15. __sudo docker exec -it [container id] cat /etc/nginx/nginx.conf__ - вывести содержимое конфигурационного файла


16. ____