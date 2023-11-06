# Установка

Перейти на страницу официального сайта [Git](https://git-scm.com/download/win "Перейти на сайт загрузки").
Скачать одну из двух версий из категории Standalone Installer (англ. «автономный установщик»). Узнать тип системы Windows можно в настройках.
Запустить программу установки. Обратить внимание, куда будет установлен Git. По умолчанию C:\Program Files\Git.
Проверить, что в списке устанавливаемых программ стоит галочка напротив пункта Git Bash Here — это позволит открывать консоль с Git в любой папке.
Далее установщик предложит много опций. Достаточно оставить все настройки по умолчанию. Несколько раз нажать Next (англ. «далее»), пока не начнётся процесс установки.
После окончания установки нажать Finish (англ. «завершить»).

# Первый запуск Git Bash

Запустить программу Git Bash можно двумя способами: ввести название программы в окно поиска на панели задач или открыть директорию, в которую был установлен Git - по умолчанию C:\Program Files\Git\bin и запустить файл bash.exe.
Откроется консоль, в которой будет написано имя_пользователя@имя_компьютера, ниже $ |

# Комманды консоли

## Навигация

| Команда			| Назначение								|  Перевод					|
|-------------------|:------------------------------------------|:--------------------------|
|pwd 				| показать рабочую папку 					| print working directory	|
|ls 				| отобразить содержимое директории 			| list directory contents	|
|ls -a 				| отобразить также скрытые файлы и папки, 	|							|
|					|названия которых начинаются с символа . 	|							|
|cd project 		| сменить директорию / перейди в project 	| change directory			|
|cd project/html 	| перейди в папку html, которая находится в |							|
|					|папке project 								|							|
|cd .. 				| перейди выше, в родительскую папку		|							|
|cd ~ 				| перейди в домашнюю папку (/Users/Username)|							|
|cd / 				| перейди в корневую директорию.			|							|

## Работа с файлами и папками. Создание

| Команда			| Назначение								|  Перевод					|
|-------------------|:------------------------------------------|:--------------------------|
|touch index.html 	| создай файл index.html в текущей папке 	| touch - «коснуться») 		|
|mkdir project		| создать директорию/папку с именем project | make directory			|
|					|в текущей папке 							| make directory			|


>touch index.html style.css script.js - если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел

## Копирование и перемещение

|Команда			| Назначение								|  Перевод					|
|-------------------|:------------------------------------------|:--------------------------|
|cp file.txt ~/dir	| копировать файл в другое место 			| copy						|
|mv file.txt ~/dir 	| перемести файл или папку в другое место 	| move						|

## Чтение

|Команда			| Назначение								|  Перевод					|
|-------------------|:------------------------------------------|:--------------------------|
|cat file.txt 		| объединить и распечатать содержимое 		|							|
|					|текстового файла file.txt 					| concatenate and print		|

## Удаление

|Команда			| Назначение								|  Перевод					|
|-------------------|:------------------------------------------|:--------------------------|
|rm about.html 		| удалить файл about.html 					| remove					|
|rmdir images  		| удалить директорию/папку images 			| remove directory			|
|rm -r project 		| удалить папку project и всё содержимое	| remove					|

### Полезные возможности

> Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.

git version - узнать версию установленной Git 
git config --global user.name "UserName" - имя или ник нужно написать латиницей и в кавычках 
git config --global user.email username@mail.com - здесь нужно указать свой настоящий email 
$ git config --global user.name "UserName" 
$ git config --global user.email "UserName@mail.com" 
cat ~/.gitconfig - Все глобальные настройки Git хранит в файле .gitconfig в домашней директории. Команда запишет в этот файл указанные имя и почту. Чтобы убедиться в этом, можно вызвать команду для чтения файлов. 
git config --list

Сделать папку репозиторием — git init 
Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием (от англ. repository — «хранилище»). Для этого следует переместиться в неё и ввести команду git init (от англ. initialize — «инициализировать»). 
cd ~/dev/first-project # перешли в нужную папку 
git init # создали репозиторий 

«Разгитить» папку, если что-то пошло не так, — rm -rf .git 
Если вы случайно сделали Git-репозиторием не ту папку, её можно «разгитить». Для этого нужно удалить скрытую подпапку .git. 
$ cd <папка с репозиторием> # перешли в папку 

$ rm -rf .git # удалили подпапку .git 
Проверить состояние репозитория — git status 
git status 
Подготовить файлы к сохранению — git add 
$ touch todo.txt 
$ touch readme.txt 
создали файлы todo.txt и readme.txt 

$ git status # проверили статус 
$ git add todo.txt 
$ git add readme.txt 
$ git add --all # подготовили к сохранению все файлы в репозитории 

Выполнить коммит — git commit 
Сделать коммит можно командой git commit c ключом -m (от англ. message — «сообщение»), который присваивает коммиту сообщение. 
git commit -m ‘Мой первый коммит!’ 

git commit -m ‘Мой первый коммит!’ 

Просмотреть историю коммитов — git log 

## Инструкция по регистрации на GitHub

В правом верхнем углу главной страницы [GitHub](https://github.com/ "Главная страница GitHub") нажмите на Sign up (англ. «зарегистрироваться»).

На экране будут последовательно появляться поля для ввода.
2.1. Введите адрес электронной почты (англ. Enter your email). 
2.2. Придумайте пароль (англ. Create a password). 
2.3. Введите имя пользователя (англ. Enter a username). 

Платформа спросит, хотите ли вы получать на почту рассылку с обновлениями и новостями (англ. Would you like to receive product updates and announcements via email?). Введите y, если хотите получать рассылку, или n, если не хотите.
Нажмите кнопку Continue (англ. «продолжить»).

GitHub предложит вам пройти капчу. Сделайте это.
После прохождения капчи нажмите Create account (англ. «создать аккаунт»).
Введите короткий код, который будет отправлен на указанный вами почтовый адрес.

Поздравляем! Вы успешно зарегистрировались на крупнейшем веб-хостинге проектов GitHub. Теперь у вас есть возможность работать бок о бок с миллионами профессионалов по всему миру, обмениваться идеями и развиваться. 

## Инструкция по созданию репозитория на GitHub

Зайдите в свой профиль по ссылке https://github.com/username, где username — имя, которое вы указали при регистрации.

Эта страница — презентация вас и ваших проектов. Её видят другие пользователи. Надпись You don't have any public repositories yet (англ. «у вас пока нет публичных репозиториев») сообщает, что пока у вас нет проектов.

Создайте репозиторий. Для этого перейдите на вкладку Repositories (англ. «репозитории»), а затем нажмите на зелёную кнопку New (англ. «новый») справа.

Открылось окно создания нового репозитория. Назовите его first-project. Название удалённого репозитория необязательно должно совпадать с именем папки проекта у вас на компьютере. Но чтобы не путаться, будем называть их одинаково.

Другие поля вам пока не понадобятся. Смело нажимайте на зелёную кнопку Create repository (англ. «создать репозиторий») внизу.

Готово! Удалённый репозиторий создан. Страница с ним открывается автоматически. 

Осталось связать удалённый репозиторий с локальным, который уже есть на вашем компьютере. GitHub предоставляет для этого инструкцию (пункт …or push an existing repository from the command line).
Но прежде, чтобы упростить работу с GitHub и сделать её более безопасной, вы научитесь генерировать SSH-ключи (от англ. Secure Shell — «безопасная оболочка»)

## Генерируем SSH-ключ

```
Представьте, что у вас есть ключ от двери, за которой хранится важный документ. Чтобы получить доступ к этому документу,
вам нужно вставить ключ в замочную скважину и повернуть его. Поскольку ключ есть только у вас, ваш документ надёжно защищён
от посторонних глаз. Чтобы получить доступ к репозиторию на GitHub, вам тоже нужно предоставить ключ, который подтверждает
вашу личность и права на чтение или изменение данных. Без этого ключа доступ будет ограничен. Об этом и пойдёт речь в уроке.
Что такое SSH
Когда компьютеры обмениваются данными в сети, они следуют сетевым протоколам (англ. network protocols) — правилам обмена
данными между компьютерами.
Один из наиболее распространённых сетевых протоколов — SSH (от англ. Secure Shell Protocol). Он обеспечивает безопасный обмен
данными в сети. С помощью этого протокола можно получать данные с удалённого компьютера или отправлять их на него. Трафик
шифруется, поэтому протокол безопасен.
SSH использует пару ключей для обеспечения безопасности — публичный и приватный: 
Приватный ключ (англ. private key) хранится только на вашем компьютере и не должен передаваться кому-либо ещё.
Он используется для расшифровки данных.
Публичный ключ (англ. public key) доступен всем и используется для шифрования данных.
Они могут быть расшифрованы парным приватным ключом.
Только вы можете расшифровать данные с помощью приватного ключа, но любой владелец публичного ключа может их для вас зашифровать.
Эти два ключа связаны и образуют SSH-пару. В будущем вы наверняка будете использовать их для взаимодействия с GitHub и другими
удалёнными серверами.
```

## Создание ключа шифрования SHH

Проверка наличия SSH-ключа
 cd ~ перейти в домашнюю директорию
 ls -la .ssh/ вывели список созданных ключей

## Инструкция по генерации SSH-ключа

Для генерации SSH-пары можно использовать программу ssh-keygen. Откройте терминал и введите следующую команду.
 ssh-keygen -t ed25519 -C "User@mail.com" - электронная почта, к которой привязан ваш аккаунт на GitHub" 
Generating public/private rsa key pair. - сгенерированы публичный и приватный ключи
Укажите место хранения ключей. Простой вариант — сделать домашний каталог пользователя путём по умолчанию. Для этого нажмите Enter.
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again] 
Программа запросит кодовую фразу (англ. passphrase) для доступа к SSH-ключу. Вы можете оставить поле пустым. Для этого нажмите Enter, а затем ещё раз Enter для подтверждения.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/UserName/.ssh/id_ed25519
Your public key has been saved in /c/Users/UserName/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:u+jW2SUszanEX/1BdH0cr0PDOQYSfCZ3F0CMW2+D6dM UserName@mail.com
The key's randomart image is:
+--[ED25519 256]--+
|         .o.=o.++|
|          oo+=.oB|
|           =o.%.+|
|           . = O |
|       .S+ ...* .|
|        +.* oo.E |
|       o.* +  ...|
|      ..+.o     .|
|     oo .        |
+----[SHA256]-----+

ls -a ~/.ssh 

## Инструкция по связыванию SSH-ключа и GitHub-аккаунта

В директории ~/.ssh будет создано два файла — id_ed25519 и id_ed25519.pub (или id_rsa и id_rsa.pub — в зависимости от выбранного алгоритма шифрования):
id_ed25519/id_rsa — приватный ключ (файл без .pub в конце). Ни в коем случае не копируйте его и не делитесь им.
id_ed25519.pub/id_rsa.pub — публичный ключ (на это указывает расширение .pub).
Скопируйте содержимое файла с публичным ключом в буфер обмена.

## для macOS
скопировать содержимое ключа в буфер обмена:
```
$ pbcopy < ~/.ssh/id_rsa.pub
для ed25519:
$ pbcopy < ~/.ssh/id_ed25519.pub 
Здесь используется команда pbcopy — она копирует поток данных в буфер обмена. 
Запись pbcopy < ~/.ssh/id_rsa.pub означает: «Скопируй в буфер обмена всё 
содержимое файла ~/.ssh/id_rsa.pub».
```
В качестве альтернативы вы можете распечатать файл на экран с помощью cat ~/.ssh/id_rsa.pub и скопировать его вручную.

## для Windows
скопировать содержимое ключа в буфер обмена:
```
$ clip < ~/.ssh/id_rsa.pub
для ed25519:
$ clip < ~/.ssh/id_ed25519.pub 
Если clip не сработает, выведите содержимое файла с помощью 
cat ~/.ssh/id_rsa.pub или cat ~/.ssh/id_ed25519.pub и 
скопируйте вывод в буфер обмена из консоли.
```
Перейдите на GitHub и выберите пункт Settings (англ. «настройки») в меню аккаунта.

В меню слева нажмите на пункт SSH and GPG keys.

В открывшейся вкладке выберите New SSH key (англ. «новый SSH-ключ»).

В поле Title (англ. «заголовок») напишите название ключа. Например, Personal key (англ. «личный ключ»).
В поле Key type (англ. «тип ключа») должно быть Authentication Key (англ. «ключ аутентификации»).
В поле Key скопируйте ваш ключ из буфера обмена.


8. Нажмите на кнопку Add SSH key (англ. «добавить SSH-ключ»).

Проверьте правильность ключа с помощью следующей команды.
$ ssh -T git@github.com 
Если это первый раз, когда вы используете Git, чтобы поделиться проектом на GitHub, появится похожее предупреждение.
The authenticity of host 'github.com (140.82.121.4)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Это предупреждение сообщает, что вы никогда не соединялись с сервером GitHub. Поэтому Git не может гарантировать, что сервер является тем, за кого он себя выдаёт.
Для подтверждения подлинности сервер генерирует и публикует ключи SHA256. Вы можете проверить ключи GitHub по этой ссылке. Если ключ в предупреждении совпадает с тем, что вы видите на сайте, значит, сервер является действительным. Введите yes, чтобы продолжить. Вы увидите приветствие на экране.
Hi %ВАШ_АККАУНТ%! You've successfully authenticated, but GitHub does not provide shell access. 
Если у вас возникли сложности при генерации или привязке SSH-ключей, посмотрите видеоинструкцию, в которой мы показываем всё по порядку.

## Привязать удалённый репозиторий к локальному — git remote add

Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно.
git@github.com:UserName/project.git
git remote add origin git@github.com:UserName/project.git

В командную строку нельзя вставить текст из буфера обмена с помощью привычного сочетания Ctrl+V. На Windows (в Git Bash) и Linux для этого используется сочетание Ctrl+Shift+V, а на macOS — Cmd+V.
Также можно нажать правую кнопку мыши и выбрать пункт Paste (англ. «вставить») в выпадающем меню.
origin (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один). Это значительно упрощает работу.
Убедиться, что репозитории связаны, — git remote -v
git remote -v
origin git@github.com:UserName/project. (fetch)
origin git@github.com:UserName/project. (push)

В выводе вы должны увидеть две строчки, аналогичные тем, что показаны выше.
Флаг -v — короткая форма флага --verbose (англ. «подробный»). Он позволяет показать больше информации в выводе.

Отправить изменения на удалённый репозиторий — git push

В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.

git config --list
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/etc/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=UserName
user.email=UserName@mail.com
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
remote.origin.url=git@github.com:UserName/project.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*

git push -u origin master

$ git push -u origin master
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 20 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (14/14), 1.27 KiB | 1.27 MiB/s, done.
Total 14 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:UserName/project.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

В дальнейшем при работе с удалённым репозиторием флаг -u можно опустить и писать просто git push.

Преимущество README.md в том, что средства командной работы (такие, как GitHub) могут отображать его содержимое в браузере в виде удобной разметки. Для этого нужно не просто залить текст, но и настроить шрифт, заголовки и отступы с помощью markdown. Маркда́ун — это специальный язык разметки. Он позволяет красиво отформатировать текстовый документ.

# Шпаргалка markdown

## Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

## Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

## Выделение кода

Чтобы выделить текст как код, поместите его в тройные кавычки `````. 

```
mkdir my_project
cd my_project
git init
```
```
Это лишь некоторые функции markdown. 

Ссылки
Чтобы сделать ссылкой часть текста, его заключают в квадратные скобки, а затем указывают нужный адрес в круглых скобках.
[Яндекс](https://www.yandex.ru) 
Также можно добавить ссылке тайтл (от англ title — «название», «заголовок»). Тайтл — это всплывающая подсказка, которая появляется при наведении мыши на ссылку. Тайтл нужно заключить в кавычки и указать внутри скобок после адреса.
[Яндекс](https://www.yandex.ru "Я Yandex!") 


# Хеш — идентификатор коммита

Что такое хеш. Хеширование коммитов
Хеширование (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. fingerprint).
Информация о коммите — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит.
Git хеширует (преобразует) информацию о коммите с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») и получает для каждого коммита свой уникальный хеш — результат хеширования.

Обычно хеш — это короткая (40 символов в случае SHA-1) строка, которая состоит из цифр 0—9 и латинских букв A—F (неважно, заглавных или строчных). Она обладает следующими важными свойствами:
если хеш получить дважды для одного и того же набора входных данных, то результат будет гарантированно одинаковый;
если хоть что-то в исходных данных поменяется (хотя бы один символ), то хеш тоже изменится (причём сильно).
Чтобы убедиться в этом, можно поэкспериментировать с SHA-1 на этом [сайте](https://emn178.github.io/online-tools/sha1.html) — попробуйте ввести в поле input (англ. «ввод») разные символы, слова или предложения и понаблюдайте, как меняется хеш в поле output (англ. «вывод»).
Хеш — основной идентификатор коммита
Git хранит таблицу соответствий хеш → информация о коммите. Если вы знаете хеш, вы можете узнать всё остальное: автора и дату коммита и содержимое закоммиченных файлов. Можно сказать, что хеш — основной идентификатор коммита.
При работе с Git хеши будут встречаться регулярно. Их можно будет передавать в качестве параметра разным Git-командам, чтобы указать, с каким коммитом нужно произвести то или иное действие.
Все хеши и таблицу хеш → информация о коммите Git сохраняет в служебные файлы. Они находятся в скрытой папке .git в репозитории проекта.
=======
>>>>>>> ec5e1f4b1ee7985aab1a4a70059cec9f645a0ff1
