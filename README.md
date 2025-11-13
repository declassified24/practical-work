Практическая работа №3
1. Установка Git
Шаги установки:
1.	Перейдите на сайт: https://git-scm.com/download/win
2.	Скачайте установщик для Windows
3.	Запустите установщик и следуйте инструкциям

Проверка установки:
powershell
git --version

Ожидаемый результат: git version 2.51.2.windows.1

2. Установка Docker
Шаги установки:
1.	Перейдите на сайт: https://docs.docker.com/desktop/install/windows-install/
2.	Скачайте Docker Desktop для Windows
3.	Запустите установщик Docker Desktop
4.	После установки перезагрузите компьютер
5.	Запустите Docker Desktop из меню Пуск

Проверка установки:
powershell
docker --version

Ожидаемый результат: Docker version 28.5.1, build e180ab8

3. Установка Docker Compose
Проверка установки:
powershell
docker-compose --version
Ожидаемый результат: Docker Compose version v2.40.2-desktop.1

 
4. Скриншоты версий ПО
Выполните команды и сделайте скриншот:

powershell
git --version
docker --version
docker-compose --version

Сохраните скриншот командной строки с выводом всех трёх команд.

![Screenshot](https://github.com/declassified24/practical-work/blob/develop/images/31.png)

5. Создание рабочей директории

Создайте папку для проекта:
# Переход на диск E:
E:

# Создание основной папки
mkdir 2
cd 2

# Создание папки проекта
mkdir practical-work
cd practical-work

Теперь вы находитесь в папке: E:\2\practical-work\

6. Запуск контейнера Nginx с текстом "GRGU"
Шаги выполнения:

powershell
# 1. Создайте папку для сайта
mkdir website

# 2. Создайте файл index.html с текстом "GRGU"
echo "<html><body><h1>GRGU</h1></body></html>" > website/index.html

# 3. Запустите контейнер Nginx (правильная команда для PowerShell)
$currentPath = Get-Location
docker run -d --name nginx-container -p 8080:80 -v "${currentPath}\website:/usr/share/nginx/html" nginx

Проверка результата:
powershell
docker ps

# Должен показать контейнер nginx-container
1.	Откройте браузер
2.	Перейдите по адресу: http://localhost:8080
3.	Вы должны увидеть страницу с большим текстом "GRGU"

![Screenshot](https://github.com/declassified24/practical-work/blob/develop/images/32.png)
 
7. Создание README.md файла
powershell
echo "# Practical Work - GRGU" > README.md

8. Добавление описания в README.md
Открыл файл README.md в редакторе и добавил всю нужную информамацию



9. Сохранение в ветке develop и загрузка на удалённый сервер

# 1. Инициализация Git 
git init

# 2. Настройка пользователя
git config user.name "declassified24"
git config user.email "valet@example.com"

# 3. Создание ветки develop
git checkout -b develop

# 4. Добавление всех файлов
git add .

# 5. Создание коммита
git commit -m "Practical work: Nginx with GRGU page"

# 6. Добавление удалённого репозитория 
git remote add origin https://github.com/declassified24/practical-work.git

# 7. Отправка на GitHub
git push -u origin develop

Ссылка на проект:
https://github.com/declassified24/practical-work

![Screenshot](https://github.com/declassified24/practical-work/blob/develop/images/33.png)
 
Проверка выполнения на каждом этапе:

# Проверка статуса Git
git status

# Проверка текущей ветки
git branch

# Проверка удалённых репозиториев
git remote -v

# Проверка контейнеров
docker ps

# Проверка файлов в папке
ls



