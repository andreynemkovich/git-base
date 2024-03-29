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

* Файл HEAD

Файл `HEAD` — один из служебных файлов папки `.git`. Он указывает на коммит, который сделан последним (то есть на самый новый).  
Внутри `HEAD` — ссылка на служебный файл: `refs/heads/master` (или `refs/heads/main` в зависимости от названия ветки). Если заглянуть в этот файл, можно увидеть хеш последнего коммита.  
Вместо хеша последнего коммита можно написать слово `HEAD`.

* Стили оформления сообщений к коммитам

```bash
$ git commit -m "LGS-239: Дополнить список пасхалок новыми числами"
# номер задачи: что сделано - всего до 72 символов, чтобы влазило в git log --onelene
```

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
# полный лог
$ git log --oneline
# сокращённый лог
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

* Отправить изменения на удалённый репозиторий

```bash
$ git push -u origin main
# в первый раз передаётся флаг -u (сязывает локальную ветку с одноимённой удалённой)
# в последующие разы - просто git push
```

* Статусы файлов git

```bash
$ git status
# проверить статусы файлов
```

![untracked, modified, staged+tracked, tracked](https://github.com/andreynemkovich/git-base/blob/main/git-files-statuses.png?raw=true "Вот картинка")

* Добавление изменений в последний коммит

`git commit --amend --no-edit` - добавь изменения к последнему коммиту и оставь сообщение прежним;

`git commit --amend -m "Новое сообщение"` — измени сообщение к последнему коммиту на Новое сообщение.

* Откат файлов и коммитов

`git restore --staged hello.txt` — переведи файл hello.txt из состояния staged обратно в untracked или modified;

`git restore hello.txt` — верни файл hello.txt к последней версии, которая была сохранена через git commit или git add;

`git reset --hard b576d89` — удали все незакоммиченные изменения из staging и «рабочей зоны» вплоть до указанного коммита.

* Просмотр изменений

`git diff` — покажи изменения в «рабочей зоне», то есть в modified-файлах;

`git diff a9928ab 11bada1` — выведи разницу между двумя коммитами;

`git diff --staged` — покажи изменения, которые добавлены в staged-файлах.

* Клонирование чужого репозитория

`git clone git@github.com:YandexPraktikum/first-project.git` - склонируй репозиторий с URL first-project.git из аккаунта YandexPraktikum на мой локальный компьютер.

* Создание веток

`git branch feature/the-finest-branch` — создай ветку от текущей с названием feature/the-finest-branch;

`git checkout -b feature/the-finest-branch` — создай ветку feature/the-finest-branch и сразу переключись на неё.

* Навигация по веткам

`git branch` — покажи, какие есть ветки в репозитории и в какой из них я нахожусь (текущая ветка будет отмечена символом *);

`git branch -a` — покажи все известные ветки, как локальные (в локальном репозитории), так и удалённые (в origin, или на GitHub);

`git checkout feature/br` — переключись на ветку feature/br.

* Сравнение веток

`git diff main HEAD` — покажи разницу между веткой main и указателем на HEAD;

`git diff HEAD~2 HEAD` — покажи разницу между тем коммитом, который был два коммита назад, и текущим.

* Удаление веток

`git branch -d br-name` — удали ветку br-name, но только если она является частью main;

`git branch -D br-name` — удали ветку br-name, даже если она не объединена с main.

* Слияние веток

`git merge main` — объедини ветку main с текущей активной веткой. 

* Работа с удалённым репозиторием

`git push -u origin my-branch` — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто git push без -u;

`git push my-branch` — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории;

`git pull` — подтяни изменения текущей ветки из удалённого репозитория.

##  PR

### Алгоритм для создания PR

- Склонировать репозиторий.
- Если вы не участник проекта, предварительно сделать «форк» исходного репозитория.
- На странице репозитория или «форка» нажать кнопки: Code → SSH → скопировать ссылку.
- Выполнить команду git clone <ссылка на репозиторий>.
- Создать ветку для вашей задачи: git checkout -b my-task-branch-name.
- Добавить и «закоммитить» изменения, которые вы хотите внести в проект.
- «Запушить» ветку: git push --set-upstream origin HEAD или git push -u origin my-task-branch-name.
- GitHub (с помощью Git) выведет ссылку на создание PR. По ней нужно перейти.
- PR можно также создать через интерфейс GitHub.
- Сообщить о пул-реквесте ревьюеру.
- Обсуждать с ревьюером предлагаемые изменения и вносить правки, пока эти изменения не будут одобрены (пока не будет получен «апрув»).  

### Если кто-то добавил конфликтующие изменения в main, пока ваш PR был на ревью, нужно разрешить конфликт.  

- Обновить main: git checkout main && git pull.
- Влить main в свою ветку: git checkout my-task-branch-name && git merge main.
- Разрешить конфликты слияния с помощью IDE или вручную.
- Создать коммит слияния: git commit --no-edit или git commit -m 'merge main'.
- Сделать git push своей ветки.
- Нажать кнопку Merge или подождать, пока её нажмёт кто-то ещё.
- Ещё раз обновить main, чтобы «подтянуть» ваши изменения в основную ветку локального репозитория: git checkout main && git pull.
Вы великолепны! Можете начинать снова со второго пункта.

### Алгоритм для разрешения конфликтов слияния

- Открыть проект в IDE (VS Code, IDEA или другие).
- Открыть файл, в котором есть конфликт.
- Выбрать, какие части файла нужно взять из одной ветки, а какие — из другой.
- Когда конфликты разрешены, сделать коммит: git commit --no-edit или git commit -m 'merge branch <название ветки>'.
