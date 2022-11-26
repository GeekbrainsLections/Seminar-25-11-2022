# Инструкция по работе с Git.

## Что такое Git

Система контроля версий — это система, записывающая изменения в файл или набор файлов в течение времени и позволяющая вернуться к определённой версии.

Git это наиболее популярная реализация распределенной системы контроля версий (СКВ).

Основное отличие Git от любой другой СКВ — это подход к работе со своими данными. 

Большинство систем СКВ хранят информацию в виде списка изменений в файлах.

Git не хранит и не обрабатывает данные таким способом. 
Подход Git к хранению данных больше похож на набор снимков файловой системы. Каждый раз, когда сохраняется состояние  проекта в Git, система запоминает, как выглядит каждый файл в этот момент, и сохраняет ссылку на этот снимок. Для увеличения эффективности, если файлы не были изменены, Git не запоминает эти файлы вновь, а только создаёт ссылку на предыдущую версию идентичного файла, который уже сохранён. Git представляет свои данные как поток снимков. Это делает Git больше похожим на миниатюрную файловую систему с мощными утилитами, надстроенными над ней.

## Подготовка репозитория

Для создания репозитория в папке предполагаемого репозитория используется команда ***git init***.

Эта команда создаёт в текущей папке (каталоге) новый подкаталог с именем .git, содержащий все необходимые файлы репозитория — структуру Git репозитория.

В терминале с открытой папкой-репозиторием необходимо написать ***git init***.

## Создание сохранений (коммитов)

Каждый файл в рабочем каталоге может находиться в одном из двух состояний: под версионным контролем (отслеживаемые) и нет (неотслеживаемые). 

Отслеживаемые файлы — это те файлы, которые были в последнем снимке состояния проекта; они могут быть неизменёнными, изменёнными или подготовленными к коммиту. Отслеживаемые файлы — это те файлы, о которых знает Git.

Неотслеживаемые файлы — это всё остальное, любые файлы в рабочем каталоге, которые не входили в последний снимок состояния и не подготовлены к коммиту.

### Определение состояния файла

Для определения, какие файлы в каком состоянии находятся применяется команда ***git status***. 

Понять, что новый файл неотслеживаемый можно по тому, что он находится в секции «Untracked files» в выводе команды status. Статус Untracked означает, что Git видит файл, которого не было в предыдущем коммите (снимке файловой системы). Git не станет добавлять его в коммиты без соответствующей команды. 

В терминале с открытой папкой-репозиторием необходимо написать ***git status***.

### Добавление файлов к коммиту

Чтобы начать отслеживать (добавить под версионный контроль) файл - для добавление файла к коммиту используется команда ***git add***. 

Когда файл проиндексирован, он находится в секции «Changes to be committed».

Для того, чтобы после создания нового файла в папке-репозитории добавить файл к новому коммиту необходимо в терминале с открытой папкой-репозиторием написать ***git add <имя файла>***.

### Создание коммитов

Когда индекс файла находится в состоянии отслеживания нужно зафиксировать изменения - создать коммит. 

+ Запомнить! Всё, что не проиндексировано — любые файлы, созданные или изменённые, и для которых не выполнена операция ***git add*** после редактирования — не войдут в коммит и изменения не будут отслежены. 

Для создания коммитов используется команда ***git commit***. Для этого в терминале с открытой папкой-репозиторием необходимо написать ***git commit -m <сообщение коммиту>***. 
* **Сообщение коммиту писать ОБЯЗАТЕЛЬНО!**

===========================================

*       ПРАВИЛО ТРЕХ СОХРАНЕНИЙ - (ассоциативно запоминаем : камень - ножницы - бумага) для корректной работы с файлом в Git:
 1. Шаг 1 - сохраняем изменения в файле (окно файла) - на клавиатуре в английской раскладке отжимаем "Ctrl + S"; 
 2. Шаг 2 - сохраняем изменение файла -  в терминале с открытой папкой-репозиторием написать ***git add <имя файла>***;
 3. Шаг 3 - создать коммит для записи изменения - в терминале с открытой папкой-репозиторием написать ***git commit -m <сообщение коммиту>***.

 ==========================================

## Игнорирование файлов

Если имеются файлы, которые нет необходимости автоматически добавлять в репозиторий и  видеть в списках неотслеживаемых - в таком случае, можно создать специальный файл **.gitignore**. 

В файле **.gitignore** указать неотслеживаемые файлы.

## Журнал изменений (просмотр истории коммитов)

После создания несколько коммитов или клонирования репозитория с существующей историей коммитов, понадобится возможность посмотреть что было сделано — историю изменений (историю коммитов). 

Для просмотра истории изменений используется команда ***git log***. Для этого в терминале с открытой папкой-репозиторием необходимо набрать ***git log***.
В выпадающем списке коммитов каждый коммит имеет свой уникальный номер (SHA-1 контрольную сумму).

По умолчанию (без аргументов) ***git log*** перечисляет коммиты, сделанные в репозитории в обратном к хронологическому порядке — последние коммиты находятся вверху. Данная команда перечисляет коммиты с их SHA-1 контрольными суммами, именем и электронной почтой автора, датой создания и сообщением коммита.

*У команды git log — гораздо больше опций. Наиболее распространенные опции для команды git log могут быть полезными в зависимости от нужного формата вывода данных истории коммитов.*

Таблица 1. Наиболее распространенные опции для команды ***git log***

| опция | описание
|:-----|:-----
|-p |Показывает патч для каждого коммита.
|--stat |Показывает статистику измененных файлов для каждого коммита. 
|--shortstat|Отображает только строку с количеством изменений/вставок/удалений для команды --stat.
|--name-only|Показывает список измененных файлов после информации о коммите.
|--name-status |Показывает список файлов, которые добавлены/изменены/удалены.
|--abbrev-commit|Показывает только несколько символов SHA-1 чек-суммы вместо всех 40.
|--relative-date|Отображает дату в относительном формате (например, «2 weeks ago») вместо стандартного формата даты.
|--graph|Отображает ASCII граф с ветвлениями и историей слияний.
|--pretty|Показывает коммиты в альтернативном формате. Возможные варианты опций: oneline, short, full, fuller и format (с помощью последней можно указать свой формат).
|--oneline|Сокращение для одновременного использования опций --pretty=oneline --abbrev-commit.

*В дополнение к опциям форматирования вывода, команда ***git log*** принимает несколько опций для ограничения вывода — опций, с помощью которых можно увидеть определенное подмножество коммитов.*

Таблица 2. Опции для ограничения вывода команды ***git log***

| опция | описание |
|:------| :-----
|-(n)|Показывает только последние n коммитов. 
|-since, --after|Показывает только те коммиты, которые были сделаны после указанной даты.
|--until, --before|Показывает только те коммиты, которые были сделаны до указанной даты.
|--author|Показывает только те коммиты, в которых запись author совпадает с указанной строкой.
|--committer|Показывает только те коммиты, в которых запись committer совпадает с указанной строкой.
|--grep|Показывает только коммиты, сообщение которых содержит указанную строку. 
|-S|Показывает только коммиты, в которых изменение в коде повлекло за собой добавление или удаление указанной строки.

## Перемещение между изменениями (коммитами)

Для перемещения между коммитами используется команда ***git checkout***. Для этого в терминале с открытой папкой-репозиторием необходимо набрать команду с номером коммита ***git checkout <SHA-1 номер коммита>***. Номера коммитов можно посмотреть в истории коммитов, описанной в предыдущем пункте (достаточно указать первые четыре символа номера коммита). 

## Ветки в Git

Используя ветвление, происходит отклонение от основной линии разработки проекта (файла) и продолжается работа независимо от неё, не вмешиваясь в основную линию.

Git не хранит данные в виде последовательности изменений, он использует набор снимков (snapshot). Когда создается коммит, Git сохраняет его в виде объекта, который содержит указатель на снимок подготовленных данных. Этот объект так же содержит имя автора и email, сообщение и указатель на коммит или коммиты непосредственно предшествующие данному (его родителей): отсутствие родителя для первоначального коммита, один родитель для обычного коммита, и несколько родителей для результатов слияния двух и более веток.

Ветка в Git — это простой перемещаемый указатель на один из коммитов. По умолчанию, имя основной ветки в Git — ***master***. Как только начинаем создавать коммиты, ветка ***master*** будет всегда указывать на последний коммит. Каждый раз при создании коммита указатель ветки ***master*** будет передвигаться на следующий коммит автоматически.

* ### Создание новых веток

При создании новой ветки создаётся новый указатель для дальнейшего перемещения. 

Для создания новой ветки и присвоить ей имя необходимо воспользоваться командой ***git branch***.

Для того, чтобы создать новую ветку <***название ветки***> необходимо в терминале с открытой папкой-репозиторием написать ***git branch <название ветки>***

* ### Переключение веток

**Важно запомнить**. 
*При переключении веток в Git происходит изменение файлов в рабочем каталоге. При переключении на старую ветку рабочий каталог будет выглядеть так же, как выглядел на момент последнего коммита в ту ветку. Если Git по каким-то причинам не может этого сделать — он не позволит вам переключиться вообще.*

Для переключения на другую ветку необходимо воспользоваться командой ***git checkout <название ветки>***.

Для того, чтобы перейти на ветку <***название ветки***> необходимо в терминале с открытой папкой-репозиторием написать ***git checkout <название ветки>***

Для определения (контроля) количества веток и текущей отслеживаемой ветки необходимо воспользоваться командой ***git branch*** - активная ветка подсвечена и выделена цветом относительно остальных.

Для того, чтобы увидеть все ветки и определить текущую ветку необходимо в терминале с открытой папкой-репозиторием написать ***git branch***.

* ### Просмотр истории коммитов в ветках

Для просмотра истории изменений в ветках также используется команда ***git log***.
При этом ***git log*** не показывает все ветки по умолчанию.

Если выполнить команду ***git log***, то в её выводе только что созданная новая ветка  фигурировать не будет. Ветка никуда не исчезла - просто Git не знает, что именно она интересует, и выводит наиболее полезную по его мнению информацию. Другими словами, по умолчанию ***git log*** отобразит историю коммитов только для текущей ветки.

Для просмотра истории коммитов другой ветки необходимо явно указать её имя: ***git log <название ветки>***.

Чтобы посмотреть историю по всем веткам — необходимо выполнить команду с дополнительным флагом: ***git log --all***.

* ### Слияние веток и разрешение конфликтов

Для выполнения слияния одной ветки с другой веткой - нужно переключиться на ветку, в которую необходимо включить изменения, и выполнить команду ***git merge***.

**Важно помнить.** *Если рабочий каталог либо индекс содержат незафиксированные изменения, конфликтующие с веткой, на которую необходимо переключиться - Git не позволит переключить ветки. Необходимо зафиксировать все изменения и после этого переключить ветку.*

Для того, чтобы выполнить слияние ветки <***название ветки***> с другой веткой - необходимо в терминале с открытой папкой-репозиторием командой ***git checkout <название другой ветки>*** переключиться на ветку в которую необходимо выполнить слияние и (или) командой ***git branch*** удостовериться в нахождении на верной ветке, а затем выполнить слияние веток командой ***git merge <название ветки>***

Процесс слияния может быть не выполнен автоматически. Если, например, была по-разному изменена одна и та же часть одного файла в двух объединяемых ветках, Git не сможет их объединить.

Git не создал коммит слияния автоматически. Он остановил процесс до тех пор, пока не будет устранен конфликт. Чтобы в любой момент после появления конфликта увидеть, какие файлы не объединены, можно запустить команду ***git status***.

Чтобы разрешить конфликт, необходимо выбрать один из вариантов предложенных программой, либо объединить содержимое по-своему.

После устранения конфликта и добавления файла (файлов) в индекс — выполнить команду ***git commit*** для создания коммита слияния. Если коммит слияния требует дополнительных пояснений — описать как были разрешены конфликты.

* ### Удаление веток

По окончания слияния веток при отсутствии необходимости их использования - можно данные ветки удалить командой ***git branch -d***. Наработки из этих веток уже включены в другую ветку, поэтому ничего не потеряется.

Для того, чтобы удалить ветку необходимо в терминале с открытой папкой-репозиторием написать ***git branch -d <имя ветки>***.

* ### Отображение дерева коммитов в графическом виде

В Git реализована возможность просмотра истории изменений и слияний - дерева коммитов с представлением в графическом виде. Для этого используется команда ***git log --graph***.

Для просмотра дерева коммитов в графическом представлении необходимо в терминале с открытой папкой-репозиторием набрать команду ***git log --graph***.

## Работа с удалёнными репозиториями в git

### Работа с сайтом github.com

Cачала необходимо создать папку на локальном ПК и открыть ее в редакторе VS Code. С использованием ***git init*** не нужно создавать свой репозиторий. Далее необходимо перейти на сайт https://GitHub.com.

На этом сайте есть поиск, где можно нацти разных авторов и проекты. Выберем 
один из готовых репозиториев, либо свой собственный.

Интересующие файлы и скачаем так, чтобы на локальном ПК они стали локальным репозиторием. Эти файлы можно посмотреть и на самом сайте. Открывая их, можно увидеть, как они выглядят в редакторе после обработки Markdown. 

Необходимо выбрать Зелёную кнопку Code и нажать ее - появится строка с адресом.

Необходимо выбрать строку HTTPS, нажать «Копировать», и после этого понадобится новая команда внутри VS Code. 

Открываем терминал. В терминале записать новую команду Git: ***git clone<скопированный адрес>***.

В результате выполнения команды Git скопирует репозиторий, находящийся на сервисе GitHub, в локальный репозиторий. То есть на локальном компьютере появится полная копия этого репозитория - внутри созданной и открытой в терминале папки.

Вызвать команду ***git status***. Убедиться, что Cit не настроен. Появилась надпись, что это не Git-репозиторий, возникла какая-то фатальная ошибка, и программа отказывается работать дальше. То есть необходимо убедиться, что  пустая папка без каких-либо репозиториев.

Командой ***cd <название пепки скопированного репозитория>*** (change directory) — поменять директорию и перейти в папку. Вызвать команду ***git status*** и убедиться, что Cit в этой папке настроен. После чего можно работать в файлах - редактировать, создавать ветки и делать сохранения. 

### Работа с публичным репозиторием

1. Создать аккаунт на GitHub. Если этого нет - полный адрес https://GitHub.com.

2. Создать локальный репозиторий. Для этого надо создать папку, внутри неё вызвать команду git init, совершить какие-то действия, создать файлы, чтобы
появился хотя бы один коммит.

3. «Подружить» локальный и удалённый репозитории. GitHub при создании нового
репозитория подскажет, как это можно сделать.

4. Отправить (push) ваш локальный репозиторий в удалённый (на GitHub), при этом возможно потребуется авторизоваться на удалённом репозитории. Если сделать это
один раз, «подружится» редактор VS Code с GitHub, в дальнейшем эту операцию
проводить уже не понадобится.

5. Провести изменения «с другого компьютера». Можно сделать это на GitHub.

6. Выкачать (pull) актуальное состояние из удалённого репозитория.

### Создание кнопки pull request

1. Делаем форк (fork) интересующего репозитория.

2. Выполнить git clone для своей версии этого репозитория. Так появляется версия на своем аккаунте, и именно эту версию клонировать.

3. Создать ветку с предлагаемыми изменениями.

4. Произвести все изменения только в этой ветке.

5. Отправить эти изменения на свой аккаунт (push).

6. В окне на GitHub появляется возможность отправить pull request.

## Заключение

В данной инструкции рассмотрены базовые функции в Git по созданию и управлению репозиторием и его файлами, работе с изменениями и ветвлением, а также дано общее описание работы с удаленными репозиториями.