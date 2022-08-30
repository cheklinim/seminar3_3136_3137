# **Инструкция по работе с системой контроля версий Git**

![Эмблема Git](git.jpg)

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

## Инициализация репозитория

Чтобы создать (инициализировать) новый репозиторий нужно в терминале ввести команду:

    git init

Репозиторий будет создан в той папке, из которой вызывалась команда

## Проверка состояния репозитория

Чтобы проверить текущее состояние репозитория нужно ввести в терминале команду:

    git status

## Добавление изменения к отслеживанию версионности

Чтобы добавить сделанное изменение к отслеживанию (поместить в индекс) нужно ввести команду:

    git add <имя файла>

где вместо <имя файла> вводится путь к файлу относительно расположения репозитория.

## Фиксация изменений

Чтобы зафиксировать изменение используется команда:

    git commit

В таком случае откроется окно для ввоба краткого описания сделанных изменений.

Чтобы сделать это одновременно с фиксацией используется команда:

    git commit -m "комментарий"

## Просмотр истории изменений

Чтобы посмотреть историю изменений используется комада

    git log

Для просмотра изменений с выводом одного коммита в одну строку используется команда

    git log --oneline

Для просмотра всех имеющихся коммитов используется команда

    git log --all

Для просмотра лога с графическим изображением веток используется команда

    git log --graph

Все указанные флаги могут использоваться вместе:

    git log --all --oneline --graph

## Просмотр различий между изменениями

Для просмотра отличий между текущим состоянием репозитория и последним сохраненным изменением используется команда

    git diff

Можно также посмотреть разницу между любыми двуми коммитами. Для этого используется команда

    git diff <хэш1> <хэш2>

## Переключение на нужное изменение

Чтобы переключиться на нужный коммит используется команда

    git checkout <хэш>

## Ветки в Git

### Создание новой ветки

Чтобы создать новую ветку используется команда

    git branch <имя_ветки>

### Просмотр всех веток

Чтобы посмотреть какие ветки существуют и на какой мы находимся используется команда

    git branch

### Переключение между ветками

Чтобы переключиться на другую ветку используется команда

    git checkout <имя_ветки>

### Слияние веток

Чтобы влить одну ветку в другую необходимо находясь в целевой ветке (КУДА будем делать слияние) выполнить команду

    git merge <имя_вливаемой_ветки>

### Конфликты при слиянии

Если одна и та же строка в разный версиях записана по разному возникнет конфликт.
Чистый гит автоматически сохраняет оба изменения, далее требуется вручную внести нужные правки и сделать коммит.

VSСode дает возможность выбрать какое изменение сохранить (входящее, существующее или оба).

### Удаление ветки

Чтобы удалить ветку, которая больше не нужно (например после слияния) используется команда

    git branch -d <имя_ветки>

## Remote repository

Remote repository give ability to work from different locations and gadgets. 
And always have up-to-date version of working file anytime and anywere.
Also it useful when you share your project for a team, which can working on this project at the same time.
And also you can participate in third-party project which you interested in and suggest your solution of any porblem.

### Create new repository on GitHub

Firat of all create an account on GitHub. Then in profile click to button 'New' in 'Repositories' menu. 
After that GitHub give you instruction what to do.

You can create new file right on GitHub and start working with it...

…or create a new repository on the command line:

    echo "# 111" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/vfyb/111.git
    git push -u origin main

…or push an existing repository from the command line:

    git remote add origin https://github.com/user_name/repo_name.git
    git branch -M main
    git push -u origin main
    
…or import code from another repository


### Link local and remote repositories

If local repository already exist, you can upload it on GitHub. To do that create new repository on GitHub and then copy this three line of code to terminal of local repository in VSC (be sure that main branch have right name. If not - replace 'main' with 'master'):

    git remote add origin https://github.com/user_name/repo_name.git
    git branch -M main
    git push -u origin main

Now your local and remote repositories connected.

### Commands push, pull, clone

When local and remote repositories are linked (and you have full access to modify it on GitHub), you can work with your file on computer. To upload modified file on GitHub use command:

    git push

To download actual version from GitHub use command:

    git pull

You can pull any open repository from GitHub. To pull third-party repository use 'clone' command:

    git clone <https://github.com/user_name/repo_name.git>

After that you need to switch to a folder with repository:

    cd <folder_name>

**WARNING!**

You can work with this files, but **can't push** the modified file back to this repository if you don't have access from repository's owner.

### Commands fork, pull request

If you want to participate in any third-party project, follow the instruction.

1. Find repository tou interested in;
2. Click button 'Fork' (it will copy repository to your account);
3. Clone this copy to your computer;
4. !!! **Create _new branch_, don't modify master branch** !!!;
5. After changing files push it on GitHub (Terminal give you a hint how do that);