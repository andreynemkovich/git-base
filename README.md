##  Командная строка

###  Навигация по каталогам

* Вывести текущую рабочую директорию

```bash
$ pwd
```

* Сменить директорию

```bash
$ cd ..
# перейти на уровень выше, в родительский каталог
$ cd ~
# перейти в домашнюю директорию
$ cd /
# перейти в корневую директорию
```

* Вывести содержимое каталога со скрытыми файлами и каталогами

```bash
$ ls
# показать файлы и каталоги в текущей директории
$ ls -a
# также показать скрытые файлы и каталоги
```

### Операции с файлами и каталогами

* Создать файл

```bash
$ touch my-new-file.txt # создали файл my-new-file.txt
```

* Создать несколько вложенных директорий (ключ -p)

```bash
$ mkdir -p dir1/dir-inside/dir-deeper-inside
# создали папку dir-deeper-inside в папке dir-inside, которая находится в папке dir1
```

* Копировать файлы

```bash
$ cp что_копируем что_копируем что_копируем куда_копируем

$ cp index.html style.css script.js src/
# скопировали три файла (index.html, style.css и script.js) в папку src
```

* Переместить файлы или каталоги

```bash
$ mv table.csv ./very-important-files
# сначала указываем имя файла, который хотим переместить, потом путь — куда перемещаем 
```

* Удалить файлы и/или каталоги

```bash
$ rm example.txt 
# удалить файл
$ rm -r images
# удалить каталог со всем его содержимым
$ rmdir images
# удалить пустой каталог
```

* Распечатать текстовый файл в консоль

```bash
$ cat myfile.txt
# распечатать содержимое файла в консоль
```

##  Git

* Настройка Git

```bash
$ nano ~/.gitconfig
```

* Сделать текущий каталог репозиторием

```bash
$ git init
```

* Разгитить каталог

```bash
$ rm -r .git
# удалить каталог .git
```

* Проверить состояние репозитория

```bash
$ git status
```

* Добавить файлы в отслеживаемые

```bash
$ git add todo.txt
# отслеживать изменения файла todo.txt
$ git add --all
# отслеживать изменения всех файлов в репозитории
$ git add.
# Отслеживать изменения всех файлов в текущем каталоге
```

* Сделать коммит

```bash
$ git commit -m 'Пояснение к коммиту'
```

* Просматривать историю коммитов

```bash
$ git log
```

* Генерация и привязка SSH-ключей

[Видео от Яндекс Практикума](https://code.s3.yandex.net/git_Basic/SSH_Screencast.mp4)

* Привязать удалённый репозиторий у локальному

```bash
$ cd ~/dev/first-project
# перейти в каталог локального репозитория
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
# в git remote add передаётся 2 параметра: имя удалённого репозитория (origin) и ссылка на удалённый репозиторий
```

* Убедиться, что репозитории связаны

```bash
$ git remote -v
# должно появиться 
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push) 
```

