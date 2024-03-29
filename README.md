# HW_git_2


<h1 align="center"Привет, меня зовут Максим !

<h3 align="center">Как приступить к работе ?</h3>

## Где располагается репозиторий с кодом ?

Репозиторий с кодом находится прямо там, где ты сейчас читаешь это readmi, на github.com :) Вот [Тут](https://github.com/Spookyviking/HW_git_2)


## Как устроен процесс внесения своих изменений в основную кодовую базу ? Каковы правила именования веток ?

В проекте существуют ветки, отражающие различную работу над проектом. Ниже подробнее.

### Основные ветки

Ветки main и develop считаются основными ветками, их смысл состоит в том, что они существуют до тех пор, пока существует сам проект. В ветке main всегда хранится стабильная версия проекта (релиз), в ветке develop хранится текущая рабочая версия проекта.

### Вспомогательные ветки

Кроме основных веток существуют так же и вспомогательные, которые используются для добавлений фич в проект, реализации багфиксов и подготовки релизов. Каждая такая ветка существует до тех пор, пока ведётся работа над задачей, для которой она была создана, после чего она удаляется, предварительно сливаясь с одной из основных веток (или сразу с двумя), если задача была успешно выполнена.

### Используются следующие типы веток:

    Ветки функциональностей (Feature branches)
    Ветки функциональностей могут иметь произвольные названия, которые очень кратко описывают суть задачи, для которой они создаются. 
    Порождается от ветки develop и используются для внедрения в проект дополнительных функций (фич), после чего вливается обратно в develop.
    
    Ветки релизов (Release branches)
    Название имеет вид release-*. Когда появляется надобность в новом релизе, создаётся ветка релиза, происходящая от develop, в которой происходят косметические изменения, необходимые для релиза. После этого ей присваивается версия (тег) в соответствии с принятым в компании стандарте нумераций версий и она вливается в обе основные ветки, master и develop.
    
    Ветки исправлений (Hotfix branches)
    Название имеет вид hotfix-*. Если в текущей стабильной версии проекта (которая хранится в master) выявляется баг, который требует немедленного исправления, создаётся ветка багфикса (исправления), порождённая от master. После удачного исправления бага вливается в master и develop.

## Как настроить свою среду разработки ?

1. Выберите удобный для вас редактор кода — IDE. Я пользуюсь [VSCodium](https://vscodium.com) (Да здравствует опенсорс!!!!) :)
2. [Настройте](https://docs.github.com/ru/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?platform=linux) доступ к репозиторию по ключу
3. Также можно [скачать](https://github.com/Spookyviking/HW_git_2/blob/test/.gitconfig) .gitconfig, заменив имя пользователя и почту на свои. С помощью этого конфига можно автоматически настроить имя пользователя и почту в своём окружении git, а также настроить некотоыре полезные команды :)


## Инструкция для младших сотрудников по работе с ветками

### Как создать свою ветку :

    git branch имя_ветки
    git checkuut пимя_созданной_ветки

###  Как внести изменения в свою ветку:

    git add .
    git commit -m "комментарий с изменениями коротко"
    git push

### Как слить изменения своей ветки с основной кодовой базой:

    git checkout main
    git merge имя_своей_ветки
    git push

### Пояснения по командам git :

    git add .
    Добавляет все файлы (или их изменения) в данной папке в отслеживаемые для будущего коммита.
    Если закоммитить, то в коммит попадут только отслеживаемые.
    Также можно добавлять отдельные файлы
    git add somefile.js

    git commit -m "комментарий с изменениями коротко"
    Коммит - это контрольная точка, которая сохраняет изменения в отслеживаемых файлах

    git push
    Отправляет изменения (коммиты) на сервер, где лежит репозиторий

    git branch имя_ветки
    Создаёт новую ветку

    git checkout main
    Переключает на ветку для работы с ней

    git merge имя_своей_ветки
    Слияние данной ветки с той, в которой ты сейчас находишься
