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
Для этого выберем ветку где мы хотим чтобы у нас происходило сведение изменений. *git merge* - команда для объединения веток, а <new branch> - название ветки изменения которой мы хотим объединить с текущей веткой.

Например *git merge aboutGit*

## Удаление веток

Удаление веток можно призводить путем прописывания команды 'git branch -d <название ветки, которую нужно удалить>' 
