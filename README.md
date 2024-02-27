##  Командная строка

###  Навигация по каталогам

* Вывести текущую рабочую директорию

```bash
$ pwd
```

* Сменить директорию

```bash
$ cd
```

* Перейти к домашней директории

```bash
$ cd ~
```

* Вывести содержимое каталога со скрытыми файлами и каталогами

```bash
$ ls -a
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
$ rm example.txt # удалить файл
$ rm -r images # удалить каталог со всем его содержимым
$ rmdir images # удалить пустой каталог
```

* Распечатать текстовый файл в консоль

```bash
$ cat myfile.txt
# распечатать содержимое файла в консоль
```

##  Git




