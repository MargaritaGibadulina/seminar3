# **Инструкция по работе с Git**

## Что такое Git

![Логотип](images/git.jpg)
Git - это распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux. Первая версия выпущена 7 апреля 2005 года.

## Создание локального репозитория

Для того чтобы создать (инициализировать) локальный репозиторий необходимо в терминале, находясь в папке проекта набрать команду: 

    git init

## Проверка состояния репозитория

Чтобы проверить состояние репозитория используют команду:

    git status

## Добавление файла к отслеживанию

Чтобы добавить файл к отслеживанию используют команду:

    git add Название файла

## Запись изменений в репозитории Git

Для записи изменений в репозиторий Git используют команду:

    git commit

При создании коммита в репозитории можно добавить однострочное сообщение с помощью команды:

    git commit -m "comment"

Для совершения коммита, который автоматически индексирует изменения в файлах, используют команду (новые файлы при этом индексироваться не будут!): 

    git commit -a

Для создания коммита всех проиндексированных изменений и добавления к коммиту подставленный комментарий используют команду:

    git commit -am "comment"

# Просмотр истории изменений

Для просмотра изменений, внесённых в репозиторий используют команду:

    git log

# Перемещение между сохранениями

Для перемещения между сохраненными версиями испольюзут команду:

    git checkout <hash>

где hash - это идентификатор коммита, показываемый в логе. 

Для возврата к последней версии используют команду:
    
    git checkout master

# Просмотр изменений

Чтобы просматривать список изменений, внесённых в репозиторий, используют комманду:

    git diff

Просмотреть изменения относительно двух веток можно командой:
 
    git diff <commit 1> <commit 2>
    
## Ветвление 

Ветвления нужны для работы над проектом и одновременного отслеживания его версий. Ветвь разработки – это бифуркация состояния кода, что создает новый путь для его эволюции. Вы можете генерировать разные ветки Git, которые будут существовать параллельно к главной ветке. Таким образом, вы сможете упорядоченно и точно включать новые функции в ваш код.

### Создание новой ветки

Для того, чтобы создать новую ветку необходимо использовать команду:

    git branch <branch_name>
    
а так же можно использовать команду:

    git checkout -b <branch_name>

Эти команды делают тоже самое, только второй вариант позволяет сразу переключиться в новую ветку. Вносить изменения в новую ветку можно сразу после ее создания.

### Удаление веток

Для удаления ветки необходимо использовать команду: 

    git branch -d <branch_name>

Если вы завершили работу над веткой и объединили её с основной, можно её удалить без потери истории. Однако, если выполнить команду удаления до слияния — в результате появится сообщение об ошибке. Этот защитный механизм предотвращает потерю доступа к файлам.

### Слияние

Объединить две ветки можно используя команду: 

    git merge <branch_name>

Данная команда объединит указанную ветку с основной. При этом вводить команду слияния необходимо из основной ветки (в которую необходимо добавить информацию).

### Конфликты

При слиянии одной ветви в другую изменения файлов из фиксаций в одной ветви могут конфликтовать с изменениями в другой.

Конфликты могут быть решены одним из нескольких вариантов: 

* Accept Current Change - принять текущую версию

* Accept Incoming Change - принять версию из ветки, с которой происходит слияние

* Accept Both Changes - принять оба варианта

* Compare Changes - сравнить варианты

## Удалённые репозитории

Удалённые репозитории нужны для...

## Загрузка новых изменений в удалённый репозиторий

Для того, чтобы загрузить сделанные локально изменения в удалённый репозиторий нужно использовать команду:

    git push
    
### Выгрузка из удалённого репозитория

    git pull