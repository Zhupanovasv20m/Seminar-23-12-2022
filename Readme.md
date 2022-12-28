# Инструкция по работе с Git

## Что такое гит?
***Git*** - самая популярная реализация распределённой системы контроля версий(версионность поддерживается и на сервере, и у каждого клиента). Самой распространнённой реализацией ***Git*** является (GitHub)[https://github.com]

## Подготовка репозитория
Для создания репозитория используется команда *git init*. Для этого необходимо открыть в терминале папку с будущем репозиторием и написать *git init*

## Создание коммитов

### Добавление файлов к коммиту
Для добавления файла к новому коммиту используется команда *git add*. Используется она следующим образом: в терминале с папкой-репозиторием пишем *git add <название файла>*.

### Создание коммита
Для создание новой фиксации(коммита) используется команда *git commit*. Для этого в терминале с папкой-репозиторием пишем *git commit -m "<сообщение к коммиту>*. Сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО!!!***

## Журнал изменений
Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*

## Перемещение между коммитами
Для перемещения на другую фиксацию(коммит) используется команда *git checkout*. Для этого необходимо, как показано в прошлом пункте, в журнале изменений найти необходимый коммит и его хеш(номер), после чего в терминале с папкой-репозиторием надо написать *git checkout <хеш коммита>*. После выполнения этой команды мы попадаем в состояние **detached head**, в котором никакие следующие коммиты сохраняться не будут. Для выхода из этого состояния необходимо написать *git checkout master*.

## Ветки в гит
### Создание веток в гит
Для создание новой ветки используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>*.
### Просмотр списка веток
Для просмотра списка веток используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch*. Выделенная зелёным со звёздочкой ветка - это ветка, в данный момент на которой мы находимся.

### Перемещение между ветками
Для перехода на другую ветку используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <название ветки>*. Такая ветка должна **существовать**.

## Слияние веток и разрешение конфликтов
Для того, чтобы соединить ветки нужно быть непосредственно на ветке *master*. Для этого воспользуйтесь командой *git checkout master*. После этого, чтобы присоединить к главное ветки другие, необходимо ввести команду *git merge <название ветки>*.
Иногда при слиянии веток могут происходить конфликты. Состояние конфликта - это такое состояние, когда в нескольких разных ветках была изменена одна и та же строка текста. Система контроля версий предлагает пользователю выбрать нужный вариант. Пользователь может выбрать один из вариантов или произвести изменения вручную. Варианты оптимизации могут быть:

1. Принять текущие изменения
2. Принять входящее изменение
3. Принять оба изменения
4. Сравнить изменения.

## Удаление веток
Для того, чтобы удалить ветку необходимо воспользоваться командой *git branch -d <название ветки>*. Важно! Если вам нужна информация с этой ветки, то прежде чем удалять, воспользуйтесь слиянием.
## Работа с удаленными репозиториями

### Что такое удаленный репозиторий
Удаленный (иногда говорят "внешний") репозиторий – это версии вашего проекта, сохраненные на удаленном сервере. Доступ к репозиторию на таком сервере может осуществляться по интернету или по локальной сети.

### Добавление локального репозитория в удаленный репозиторий
Для того, чтобы добавить локальный репозиторий в удаленный, необходимо во-первых иметь удаленный репозиторий и ссылку на него, а во-вторых открыть на компьютере локальный репозиторий. Далее в терминале с локальным репозиторием необходимо ввести следующие команды:
1. *git branch -M master*
2. *git remote add origin <ссылка на удаленный репозиторий>*
3. *git push origin master*

После этого всего в удаленном репозитории отобразится локальный репозиторий

Добавление изменений с удаленного репозитория в локальный

Для того, чтобы соединить удаленный репозиторий с локальным, то есть внести изменения, которые были произведены в удаленном репозитории, в локальный репозиторий, необходимо ввести в терминале команду *git pull origin master*.
