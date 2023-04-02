# ***Инструкция по работе с Git***

## ***Что такое GIT?***
***Git*** — распределённая система управления версиями. Проект был создан *Линусом Торвальдсом* для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года.

---

### ***Особенности GIT***
В системе *GIT* данные представляют собой набор снимков состояния миниатюрной файловой системы. Каждый раз, когда вы создаете новую версию или сохраняете состояние проекта в *Git*, по сути, делается снимок всех файлов в конкретный момент времени и сохраняется ссылка на этот снимок. Для повышения продуктивности вместо файлов, которые не претерпели изменений, сохраняется всего лишь ссылка на их ранее сохраненные версии. *Git* воспринимает данные скорее как поток снимков состояния (stream of snapshots).

В системе *Git* для всех данных перед сохранением вычисляется контрольная сумма, по которой они впоследствии ищутся (хеш SHA-1).

Практически все операции в *Git* приводят к добавлению данных в базу. Систему сложно заставить выполнить неотменяемое действие или каким-то образом стереть данные.

***Три состояния!*** Файлы в *Git* могут находиться в трех основных состояниях: ***зафиксированном***, ***модифицированном*** и ***индексированном***.

***Зафиксированное (committed)*** состояние означает, что данные надежно сохранены в локальной базе.

***Модифицированное (modified)*** состояние означает, что изменения уже внесены в файл, но пока не зафиксированы в базе данных. 

***Индексированное (staged)*** состояние означает, что вы пометили текущую версию модифицированного файла как предназначенную для следующей фиксации.

---

### ***Первая настройка GIT***
При установке *Git* первым делом следует указать *имя пользователя* и *адрес электронной почты*. Для этого необходимо выполнить следующие две команды:
* git config --global user.name "John Doe"
* git config --global user.email johndoe@example.com

Передача параметра *--global* позволяет сделать эти настройки всего один раз, так как в этом случае *Git* будет использовать данную информацию для всех ваших действий в системе.

---

### ***Проверка настроек***
Для проверки настроек системы git следует выполнить команду "*git config --list*", которая выводит список всех обнаруженных в текущий момент параметров.

---

### ***Получение справочной информации***
Для того, чтобы получить справочную информацию по какой-либо *git-команде*, следует выполнить команду "*git <команда> --help*"

---
---

## ***Основы работы с GIT***

---

### ***Создание репозитория***
Есть два подхода к созданию Git-проекта. Можно взять существующий проект или папку и импортировать в *Git*. А можно клонировать уже существующий репозиторий с другого сервера:
1. **Инициализация репозитория в существующей папке.** 

  Чтобы начать слежение за существующим проектом, необходимо перейти в папку этого проекта и ввести команду "*git init*".

2. **Клонирование существующего репозитория**.

  Получение копии существующего репозитория выполняется командой "*git clone*". Команда *git clone <ссылка_на_удаленный_репозиторий>* по умолчанию забирает все версии всех файлов за всю историю проекта.

  ---

### ***Проверка состояния репозитория***
*git status* - отображает **состояние рабочего каталога** и раздела проиндексированных файлов. С ее помощью можно проверить индексацию изменений и увидеть файлы, которые не отслеживаются Git. Для упрощенного вывода состояния, команду необходимо применять с флагом "*-s*": "*git status -s*"/

---

### ***Добавление файлов к коммиту***
Для **добавления файлов к коммиту** используется команда *"git add"*. Для того, чтобы добавить файл к новому коммиту, необходимо в терминале с открытой папкой-репозиторием написать *"git add <имя файла>"*.

---

### ***Создание коммитов***
Для **создания коммитов (фиксации изменений)** используется команда *'git commit'*. Для этого в терминале с папкой-репозиторием необходимо написать команду *'git commit -m "<сообщение к коммиту>"*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

---

### ***Перемещение между коммитами***
Для **перемещения между коммитами**, используется команда *"git checkout"*. Для этого в терминале с папкой-репозиторием необходимо написать *"git checkout <номер коммита>"*. Номера коммитов можно посмотреть в истории коммитов, описанной в предыдущем пункте.

---

### ***Сравнение изменений***
Для **сравнения изменений в коммитах, ветках, файлах и т.** д используется команда "*git diff*". Данная команда показывает что вы отредактировали (но пока не проиндексировали) и что из проиндексированного готово к фиксации.

---

### ***Удаление файлов***
Чтобы система Git перестала работать с файлом, его нужно **удалить из числа отслеживаемых** (точнее, убрать из области индексирования) и зафиксировать данное изменение. Это делает команда "*git rm*", которая заодно удаляет указанный файл из рабочей папки, благодаря чему он исчезает из списка неотслеживаемых.

---

### ***Просмотр истории версий***
Для просмотра истории изменений используется команда "*git log*". Для этого в терминале с папкой-репозиторием необходимо набрать "*git log*".

**Распространенные параметры команды *git log*:**

| Параметр | Описание |
|----------|----------|
| -p | Показывает изменения, внесенные в каждую версию |
| --stat | Показывает статистику измененных файлов в каждом коммите |
| --shortstat | Показывает только строку с изменениями/вставками/удалениями от команды |
| --name-only | Показывает список измененных файлов после информации о коммите |
| --name-status | Показывает список измененных файлов с информацией о добавлении/зменении/удалении |
| --abbrev-commit | Показывает только первые несколько символов контрольной суммы SHA-1 вместо всех 40 |
| --relative-date | Показывает дату не в полном, а в относительном формате (например, «2 недели назад») |
| --graph | Показывает ASCII-граф истории ветвлений и слияний вместе с выводом команды log |

**Параметры, ограничивающие вывод команды _git log_:**

| Параметр | Описание |
|----------|----------|
| -(n) | Показывает только последние n коммитов |
| --since, --after | Показывает только коммиты, внесенные после указанной даты |
| --until, --before | Показывает только коммиты, внесенные до указанной даты |
| --author | Показывает только коммиты определенного автора |
| --committer | Показывает только коммиты, внесенные определенным участником |
| --grep | Показывает только коммиты с сообщением фиксации, содержащим указанную строку |
| -S | Показывает только коммиты, в которых добавленный или удаленный код совпадает с указанной строкой |

---

### ***Отмена изменений***
Необходимость отмены чаще всего возникает при слишком ранней фиксации изменений, когда вы забыли добавить в коммит какие-то файлы или ошиблись с сообщением фиксации. Для повторного сохранения версии в такой ситуации можно воспользоваться параметром "*--amend*":
* git commit –amend

---

### ***Повторное сохранение версии***
Необходимость отмены чаще всего возникает при слишком ранней фиксации изменений, когда вы забыли добавить в коммит какие-то файлы или ошиблись с сообщением фиксации. Для повторного сохранения версии в такой ситуации можно воспользоваться параметром "*--amend*":
* git commit –amend

Если после фиксации очередной версии вы обнаружили, что забыли проиндексировать изменения в одном из файлов, который планировалось включить в новый коммит, можно сделать так:
* git commit -m <изначальный коммит>
* git add forgotten_file
* git commit --amend <новый комментарий>

---

### ***Отмена индексирования***
Для отмены индексирования следует воспользоваться командой "*git reset HEAD <имя файла>*".

---

### ***Отмена внесенных в файл изменений***
Для того, чтобы не сохранять внесенные в файл изменения, необходимо ввести команду "*git checkout -- <имя файла>*".

* **Внимание**
    
    Важно понимать степень опасности команды "*git checkout -- <имя файла>*". Все внесенные в файл изменения пропадают — вы просто копируете в этот файл содержимое другого файла. Никогда не пользуйтесь этой командой, если не уверены, что данный файл вам больше не понадобится.

---
---

## ***Ветвление в GIT***

---

### ***Суть ветвления***
Ветка в Git представляет собой всего лишь легкий, подвижный указатель на один из коммитов. По умолчанию в Git ей присваивается имя master. Как только вы начинаете создавать коммиты, появляется ветка master, указывающая на последнее зафиксированное вами состояние. При каждой следующей фиксации этот указатель автоматически смещается вперед. При создании новой ветки появляется новый указатель, который можно перемещать.

---

### ***Создание новой ветки***
Для создания новой ветки используется команда "git branch". Для этого в терминале с папкой-репозиторием необходимо написать "*git branch <название ветки>*".

---

### ***Просмотр списка веток***
Для просмотра списка веток используется команада "git branch". Для этого в папке-репозитории необходимо написать "*git branch*".

Узнать, куда именно нацелены указатели веток, позволяет команда *git log* с параметром *--decorate*:
* git log --oneline --decorate

---

### ***Слияние веток***
Для слияния двух вето необходиом перейти в ветку, с которой будет осуществляться слияние, и воспользоваться командой "*git merge*":
* git merge <название ветки>

---

### ***Конфликты при слиянии***
Если в двух ветках, которые вы собираетесь слить, вы внесли разные изменения в один и тот же файл, Git не сможет просто взять и объединить их. В этом случае Git не может автоматически создать коммит слияния. Система приостанавливает процесс до момента разрешения конфликта. 

Все, что относится к области конфликта слияния, помечено как неслитое (unmerged). Система Git добавляет к проблемным файлам стандартные метки, позволяющие открывать эти файлы вручную и разрешать конфликты.

Версия с указателем *HEAD* (из той ветки, в которую мы перешли перед выполнением команды *merge*) располагается в верхней части блока (то есть выше набора символов =======), а версия из ветки, которую мы сливаем с главной веткой показана в нижней части. Для разрешения конфликта следует или выбрать одну из версий, или каким то образом объединить их. Затем необходимо проиндексировать и зафиксировать изменения.

---

### ***Удаление веток***
Ветки, перед именами которых отсутствует символ (звездочка) в списке веток, в общем случае удаляются командой "*git branch -d <имя ветки>*". Ветки, не подвергшиеся слиянию, удалить данной командой не получится.

Просмотр списка веток, данные которых еще не слиты в другие ветки, осуществляется командой "*git branch --no-merged*".

При необходимости удалить ветку без слияния применяется команда "*git branch –D*".

---
---
## ***Удаленные репозитории***

Удаленные репозитории представляют собой версии проекта, хранимые в Интернете или где-то в сети. Их может быть несколько, и каждый в общем случае доступен вам только для чтения или же для чтения и записи.

---

### ***Отображение удаленных репозиториев***

Просмотр уже настроенных удаленных серверов осуществляется командой "*git remote*". Она дает список коротких имен для всех указанных вами областей удаленной работы. Если репозиторий был клонирован, вы должны увидеть по крайней мере источник, то есть имя, которое Git по умолчанию присваивает клонируемому серверу. Параметр -v позволяет увидеть URL-адреса, которые Git хранит для сокращенного имени:
* git remote -v

Для получения дополнительной информации о конкретном удаленном репозитории применяется команда "*git remote show [имя удаленного сервера]*"

---

### ***Добавление удаленных репозиториев***

Чтобы добавить удаленный репозиторий под коротким именем, которое упростит дальнейшие обращения к нему, используйте команду "*git remote add [сокращенное имя] [url]*":
* git remote add origin https://github.com/Zheshard/1dfd.git

---

### ***Извлечение данных из удаленных репозиториев***

Извлечение данных из удаленных проектов выполняется такой командой:
"*git fetch [имя удаленного репозитория]*". Команда "*git fetch*" помещает все данные в ваш локальный репозиторий, — она не выполняет автоматическое слияние с ветками, с которыми вы работаете в данный момент, и вообще никак не затрагивает эти ветки.

Команда "*git pull*" будет автоматическиизвлекать информацию из удаленной ветки и выполнять слияние с текущей веткой.

---

### ***Отправка данных в удаленный репозиторий***

Чтобы отправить данные в удаленный репозиторий, используется команда "*git push [имя удаленного сервера] [ветка]*":
* git push origin master

Команда сработает только при условии, что клонирование осуществлялось с сервера, где у вас есть доступ на запись, и за это время никто не отправлял туда свои данные. Если вы выполнили клонирование одновременно с другим пользователем и он уже отправил результаты своей работы на сервер, ваша попытка отправки данных окончится неудачей. Вам сначала нужно скачать все добавленное этим пользователем и встроить это в свои данные, и только после этого появится возможность воспользоваться командой *push*.

---

### ***Удаление и переименование удаленных репозиториев***

Переименование ссылок осуществляется командой "*git remote rename*", меняющей сокращенные имена удаленных репозиториев:
* git remote rename pb paul

Если по какой-то причине требуется удалить ссылку на удаленный репозиторий (например, вы поменяли сервер, больше не используете конкретное зеркало или участник проекта перестал вносить в него вклад), используйте команду "*git remote rm*":
* git remote rm paul

---

### ***Порядок работы с удаленным репозиторием***

1. Создать локальный репозиторий.
2. Создать удаленный репозиторий на GitHub
3. Связать локальынй и удаленный репозиторий
4. Отправить локальный репозиторий на удаленный (push)
5. После изменений данынх на удаленном репозитории, выкачать (pull) актуальное состояние из удаленного репозитория.

### ***Порядок отправки "Pull reqest"***

1. Делаем "Fork" интересующего нас репозитория
2. Делаем "git clone" для нашей версии этого репозитория
3. Создаем ветку с предлагаемыми изменениями.
4. Производим все изменения только в этой ветке
5. Отправляем эти изменения на свой аккаунт (push)
6. На GitHub появляется возможность отправить "Pull request". Делаем "Pull request".

