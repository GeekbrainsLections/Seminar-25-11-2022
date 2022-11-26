#2QWERRTY

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

11. git pull 

Эта команда используется для извлечения только что полученной информации и ее загрузки в локальный репозиторий. git pull запускает немедленное обновление локального репозитория.

12. git branch Эта команда используется для создания, просмотра переименования и удаления ветки, на которой вы сейчас находитесь. 

git branch -a

Эта команда используется для предварительного просмотра всех веток в удаленном репозитории.

git branch -r

Эта команда используется для предварительного просмотра всех веток на сервере.


13. git checkout

Пример: git checkout master или git checkout develop

Эта команда используется для переключения на ветки, которые вы уже посещали ранее.

git checkout — ещё один  вариант использования


14. git merge

Эта команда используется для объединения двух веток. Для этого укажите ветку, которую вы хотите унаследовать изменения. И имя ветки, которое вы будете использовать вместе с этой командой, — это ветка, которая предоставит изменения.

Пример: git merge develop

Здесь основная ветка наследует код из ветки разработки.


15. git merge — abort

Эта команда используется для отмены слияния.

Если нет ошибок, слияния будут успешными. Следовательно, это прерывание можно использовать только в ситуациях, когда слияние не удалось. Как понять, что нужно использовать эту команду? Ваш терминал скажет, что слияние не удалось. Он также может предложить вам исправить конфликты слияния.

Вот ещё один признак: ~/NextCloud/Documents/Web Projects/Cloud4Y (master)

Посмотрите в самый конец строки. В скобках написано (master). Это потому, что мы находимся в основной ветке. Если вы находитесь в ветке разработки, это будет означать (develop). Если смерджить не получилось, появится надпись (master|merging) или что-то в этом роде. 

git merge -X theirs

Пример: git merge -X theirs develop

Эта команда используется для объединения двух веток. И если есть конфликты слияния, эта команда просто предположит, что вы предпочитаете изменения, сделанные в указанной ветке (а не в текущей).


16. git reset — hard HEAD

Эта команда удалит все изменения, внесенные вами в ваш локальный репозиторий, и обновит его до последней версии, которая была закоммичена на GitHub.


17. git reset HEAD^

Эта команда перемещает текущую ветку назад на два коммита, эффективно удаляя два снапшота, которые мы только что создали, из истории проекта. Он отменяет случайное закоммичивание и сохраняет изменения.


18. git clean -f

Эта команда используется для удаления неотслеживаемых файлов из  вашего локального репозитория.

git clean -d

Эта команда используется для удаления неотслеживаемых директорий в вашем локальном репозитории. Вы также можете объединить его с git clean -fd, чтобы сделать и то, и другое.


19. git rm -r — cached

Пример: git rm -r --cached config.js

Эта команда используется для удаления файла из удаленного репозитория (GitHub), не удаляя его в локальном репозитории.


20. git bisect

Эта команда используется для обнаружения коммита, вызвавшего ошибку в коде. Так проще отследить коммит, где код работает и выявить проблемный коммит.


21. git diff

git diff — частое использование 

Эта команда используется сравнения изменений.


22. git rebase

Полезно, если вы работали с веткой, но затем вам нужно объединить изменения, сделанные в этой ветке, с другой. С помощью git rebase вы можете «переместить» свою ветку поверх последней версии. Это также полезно, если команда следует общепринятым соглашениям о коммитах, таким как объединение коммитов вместе или разделение «больших» коммитов на «меньшие». Это используется в основном для «реорганизации» ваших коммитов.

git rebase -i HEAD~N

Склеить коммиты, переписав историю с момента HEAD~N, т.е. с того, что было N коммитов назад. -i — означает в интерактивном режиме.


23. git stash

Эта команда используется для сохранения неподтверждённых изменений в отдельном хранилище, чтобы можно было вернуться к ним позже. Сами  файлы возвращаются к исходному состоянию. Команда полезна, когда вы работаете над одной веткой, хотите переключиться на другую, но вы ещё не готовы сделать коммит в текущей ветке. Таким образом, вы прячете изменения в коде, переключаетесь на другую ветку, возвращаетесь к исходной ветке, а затем разархивируете свои изменения.

git stash pop позволяет применить ранее отложенные изменения.
