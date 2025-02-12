# Работа с bash

## Task 1

### Command History
```bash

cd ~                                 # Открыть домашнюю директорию ~/home/TestUser
pwd                                  # Определить имя папки ~/home/TestUser
mkdir test1                          # Создать внутри каталог test1
cd test1                             # Перейти в каталог ~/home/TestUser/test1
touch test{1..3}.txt                 # Создать файл 1,2 и 3 внутри каталога test1
ls -lt                               # Проверить содержимое каталога
cd ..                                # Перейти в домашнюю директорию ~/home/TestUser
mkdir test2                          # Создать каталог test2
rmdir test2                          # Удалить каталог test2
rm ~/test1/2.txt                     # Удалить файл 2 из каталога test1
mkdir test3                          # Создать каталог test3
touch ~/test3/1.txt ~/test3/2.txt    # Создать файл 1,2 внутри каталога test3
rm -r test3                          # Удалить каталог test3
mkdir test4                          # Создать каталог test4
mv ~/test1/1.txt ~/test4/1.txt       # Переместить файл 1 из папки test1 в папку test4
mv ~/test1/3.txt ~/test4/3.txt       # Переместить файл 3 из папки test1 в папку test4

echo "line
    > line
    > line" > ~/test4/1.txt          # Добавить в файл 1 три строки со словами line

cat ~/test4/1.txt                    # Посмотреть содержимое файла 1

echo "line
    > line
    > line" > ~/test4/1.txt          # Добавить в файл 3 три строки со словами line

less ~/test4/1.txt ~/test4/3.txt     # Просмотр содержимого двух файлов (1 и 3) сразу

echo "pipeline
    > pipeline
    > pipeline" > ~/test4/1.txt      # Заменить все строки в файле 1

```

## Task 2

### Command History
```bash

cd ~                                        # Открыть домашнюю директорию ~/home/TestUser
mkdir test3                                 # Создать каталог test3
                                            # Создать файл 4,5 и 6 внутри каталога test3
touch ~/test3/4.txt ~/test3/5.txt ~/test3/6.txt    

echo "row1
    > row2
    > row3
    > row4" > ~/test3/4.txt                 # Создать внутри файла 4 строки row 1-4

echo "row1
    > row2
    > row3
    > row4" > ~/test3/5.txt                 # Создать внутри файла 5 строки row 1-4

echo "row1
    > row2
    > row3
    > row4" > ~/test3/6.txt                 # Создать внутри файла 6 строки row 1-4

grep "row2" ~/test3/5.txt                   # Найти строку row2 в файле 5

grep -r "row" ~/test3                       # Найти строку row в папке test3

grep -c "row" ~/test3/6.txt                 # Посчитать строки с содержимым row в файле 6

find ~/test3 -name "5.txt"                  # Найти файл 5 внутри папки test3

find ~/test3 -name "5.txt" -delete          # Используя команду find, удалить файл 5

echo -e "test\n" >> ~/test3/4.txt           # Используя команду echo, добавить слово test в файл 4

sed -i 's/test/fail/g' ~/test3/4.txt        # Заменить слово test в файле 4 на fail

echo -e "test\n" >> ~/test3/4.txt           # Добавить в файл 4 слово test так, чтобы сохранилось содержимое

ps aux                                      # Просмотреть все процессы для юзеров

kill 666                                    # Убить процесс 666 в консоли

ping rusau.net                              # Узнать доступность ресурса rusau.net, используя ping

ping -c 5 rusau.net                         # Отправить 5 пакетов на сайт rusau.net

                                            # Используя GET и команду curl, получить информацию о зарегистрированных питомцах с любым статусом на https://petstore.swagger.io/
curl -X GET https://petstore.swagger.io/v2/pet/findByStatus?status=pending,sold,available

                                            # Используя POST и команду curl, создать нового пользователя на https://petstore.swagger.io/
curl -X POST https://petstore.swagger.io/v2/user --data "id=777" --data "username=Astar" --data "firstName=Astarion" --data "lastName=Baldur" --data "email=AstarBaldr@mail.com" --data "password=abcde12345" --data "phone=88005553535" --data "userStatus=1"

```
