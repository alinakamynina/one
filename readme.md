1. первый коммит
2. коммит 2
3. коммит 3
4. коммит 4
8. восемь
9. девять

# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)

## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с пепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

## Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*

## Удаление веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

## Отмена вещей
На любом этапе вы можете захотеть что-то отменить. Здесь мы рассмотрим несколько основных инструментов для отмены внесенных вами изменений. Будьте осторожны, потому что вы не всегда можете отменить некоторые из этих отмен. Это одна из немногих областей в Git, где вы можете потерять часть работы, если сделаете это неправильно.

Одна из распространенных отмен происходит, когда вы делаете коммит слишком рано и, возможно, забываете добавить некоторые файлы, или вы путаете свое сообщение коммита. Если вы хотите повторить эту фиксацию, внесите дополнительные изменения, которые вы забыли, подготовьте их и снова зафиксируйте, используя --amendопцию:

$ git commit --amend

## Просмотр истории коммитов
После того, как вы создали несколько коммитов или клонировали репозиторий с существующей историей коммитов, вы, вероятно, захотите оглянуться назад, чтобы увидеть, что произошло. Самый простой и мощный инструмент для этого — git logкоманда.

Одна из наиболее полезных опций — это -pили --patch, которая показывает разницу ( вывод патча ), представленную в каждой фиксации. Вы также можете ограничить количество отображаемых записей журнала, например, использовать -2для отображения только две последние записи.
В этих примерах используется очень простой проект под названием «simplegit». Чтобы получить проект, запустите:

$ git clone https://github.com/schacon/simplegit-progit

Когда вы запустите git logэтот проект, вы должны получить вывод, который выглядит примерно так:
то делать, если вы понимаете, что не хотите сохранять изменения в CONTRIBUTING.mdфайле? Как вы можете легко не модифицировать его — вернуть его к тому, как он выглядел, когда вы в последний раз делали коммит (или первоначально клонировали, или каким-то образом вы поместили его в свой рабочий каталог)? К счастью, git statusтакже рассказывает вам, как это сделать. В выходных данных последнего примера неустановленная область выглядит так:

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   CONTRIBUTING.mdS
$ git log
commit ca82a6dff817ec66f44342007202690a93763949
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Mon Mar 17 21:52:11 2008 -0700

    Change version number

commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 16:40:33 2008 -0700

    Remove unnecessary test

commit a11bef06a3f659402fe7563abf99ad00de2209e6
Author: Scott Chacon <schacon@gee-mail.com>
Date:   Sat Mar 15 10:31:28 2008 -0700
