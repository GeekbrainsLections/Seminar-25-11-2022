# Инструкция по работе с Git

## Что такое Git?
Git - это наиболее популярная реализация распредеённой системы контроля версий. Наиболее полпулярной реализацией 

## Подготовка репозитория
Для создания репозитория в папке предпологаемого репозитория необходимо написать команду *git init*. Для этого в терминале с открытой папкой-репозиторем пишем *git init*

## Создание коммитов

### Добавление файлов к коммиту
Для добавления файлов к коммиту используется команда *git add*. Для того, чтобы добавить файл к новому коммиту необходимо в терминале с открытой папкой-репозиторием написать *git add <имя файла>*.

### Создание коммитов
Для создание коммитов используется команда *git commit*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git commit -m "<сообщение к коммиту>"*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***. 

## Журнал изменений
Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторем необходимо набрать *git log*.

## Перемещение между коммитами
Для перемещения между коммитами используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <номер коммита>*. Номера коммитов можно посмотреть в истории коммитов, описанной в предыдущем пунткте.

## Ветки в Git

### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git branch*

### Переход между ветками
Для перехода между ветками используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <название ветки>*.


### Создание новой ветки
Для создания новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*.

## Слияние веток и разрешение конфликтов

## Удаление веток

Удаление веток можно призводить путем прописывания команды 'git branch -d <название ветки, которую нужно удалить>' 

## Наиболее распространенные команды

1. git init

Эта команда используется для инициализации проекта как репозитория git.


2. git clone

Эта команда клонирует репозиторий в новую директорию. 

git config — это удобная функция, которая используется для настройки значений конфигурации Git на глобальном и локальном уровнях проекта. Примеры команд:

git config --local user.name "Name"

git config --local user.email "your_email@example.com"

 git config --global user.name "Name"

 git config --global user.email "your_email@example.com"


Если надо скопировать только файлы:

git clone --depth=1 git://someserver/somerepo dirformynewrepo

rm -rf !$/.git


3. git remote add

Пример: git remote add origin https://github.com/MrKrishnaAgarwal/Git-CheatSheet.git

Эта команда используется для добавления или подключения к удаленному репозиторию.


4. git remote -v

Эта команда используется для просмотра подключенных удаленных репозиториев.


5. git status

Эта команда используется для просмотра статуса файлов в вашем локальном репозитории. Отслеживаются ли файлы? Не отслеживается? Изменены ли они?


6. git add

Пример: git add index.html

git add index.html style.css style.scss

Эта команда переносит все новые и измененные файлы в раздел проиндексированных файлов

git add -A

Эта команда используется для индексирования ВСЕХ неустановленных файлов.

git add

для конкретного файла


7. git reset

Эта команда используется для мягкой или жёсткой отмены изменений, позволяет сбросить состояние проекта до нужного коммита. Например. 

отмена неотправленного коммита: git reset --hard HEAD^

отмена отправленного коммита ( возврат к состояние коммита 7880ae2 )

git reset --hard f7880ae2

git push origin -f


8. git commit

Эта команда совершает коммит  — «закрепляет» промежуточные результаты.

git commit -m “Text message”

Пример: git commit -m "added navigation bar"

Команда -m позволяет указать commit message без обращения к редактору

git commit --amend

Команда --amend вносит в предыдущий коммит изменения, которые подготовлены к коммиту. Используется и для редактирования предыдущего commit message, если в нём допущены ошибки.


9. git push -u origin

Ключ -u (полный вариант --set-upstream) создаёт в удалённом репозитории ветку, соответствующую локальной и связывает их.

git push

Пример: git push -u origin master

Эта команда используется для отправки закоммиченных файлов в удаленный репозиторий (также известный как GitHub) в указанной ветке. Используйте эту команду, когда вы впервые отправляете файлы в удаленный репозиторий. Он зафиксирует место, куда вы отправляете эти файлы. И в следующий раз можно будет использовать команду git push.

10. git fetch

Эта команда используется для получения самой последней версии вашего локального репозитория. Загружает коммиты, файлы и ссылки из удаленного репозитория в ваш локальный репозиторий.