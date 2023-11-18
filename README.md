# telegram-parser-v1.0. Telegram parser and inviter. Парсер и инвайтер чатов Телеграмм. (Telethon) 
__public edition__


![Watermark](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/bb1e06e4-83a5-4302-83b6-3d530fcaa14f)


## 0. Принцип работы.
Бесплатный парсер участников чата с функцией инвайта. За основу взята библиотека Telethon. Парсинг и инвайтинг осуществяется с использованием юзерботов. Нужно иметь аккаунт в телеграмме, знать свой api_id и api_hash токены (см. п.1).
## 1. Подготовка к запуску.


Перед началов нужно узнать свой api_id и api_hash токены. Переходим на сайт: https://my.telegram.org/apps и авторизуемся. Выбераем пункт __API Development Tools__

![12591615102022_5c20dcbcfbab07ab6c2df7e27444d5ac2afca569](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/75080769-1aa6-4cbc-ab75-cd0a1e04ec09)


В следующем окне заполняем поля: App title и Short name. Из пречня приложений выбираем desktop.

![gfbauf](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/963ca90a-b9f7-4f94-bc95-a87742742239)


Нажимаем Create Application и из возникнувшего окна сохраняем себе api_id и api_hash. 

__*Рекомендую не проводить эту процедуру на основном аккаунте, или как минимум остераться утечки ваших api_id и api_hash. C их помощью можно получить полный доступ над аккаунтом*__


## 2. Сборка проекта.


Если вы знаете python и у вас установлен PyCharm, то для вас всё просто. Скачиваете репозиторий и открываете как проект. В терминал вводите команду
``` pip install Telethon ```, а дальше разберётесь оставьте в коде свои api_id и api_hash, чтобы каждый раз их заново не вводить и в строке ```TelegramClient``` в функцию ```.start()``` в качестве аргумента передайте номер телефона на который зарегестрирован аккаунт в формате ```str```. Вот так: 

![iufg](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/99b59a0a-f9bb-4d97-a0a0-b550952dfce9)



Я старался специально упростить код, чтобы вы могли его проще модифицировать. Лицензия проекта это позволяет, только не забудьте там меня упомянуть. 

### Если вы не знакомы с python:
__Windows__
* Скачиваем python 3.12 по ссылке https://www.python.org/ftp/python/3.12.0/python-3.12.0-amd64.exe
* __!При установке обязательно ставьте галочку у Add to PATH!__ ![hgai](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/046ed050-5a00-4c94-8758-6de165e81ca3)

* Открываем командную строку(Клавиша "win" + клавиша "R" и команда ```cmd```)
* Командой ```cd``` ведём к директории парсера. Пример: ```cd C:Users/Keqy/programs/repos/telegram-parser-v1.0```
* Устанавливаем требования парсера. Команда - ```py main.py -i```, затем ```py main.py -c```
 
Удачного использования.


__Linux__
* Открываем терминал, обновляем пакеты. ```sudo apt update```
* Устанавливаем python и git. ```sudo apt install python3 python3-pip git -y```
* Скачиваем репозиторий. ```git clone https://github.com/Keqy/telegram-parser-v1.0/```
* ```cd``` в директорию парсера.
* Устанавливаем требования парсера. Команда - ```py main.py -i```, затем ```py main.py -c```

Удачного использования.

__Termux__
* Открываем терминал, обновляем пакеты. ```pkg update```
* Устанавливаем python и git. ```sudo apt install python3 python3-pip git -y```
* Скачиваем репозиторий. ```git clone https://github.com/Keqy/telegram-parser-v1.0/```
* ```cd``` в директорию парсера.
* Устанавливаем требования парсера. Команда - ```py main.py -i```, затем ```py main.py -c```

Удачного использования.

## 3. Использование.
Далее откроется меню терминала. 

![menu](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/13f05280-d6cf-40fe-806d-b0885f480758)

Чтобы спарсить участников чата, нужно чтобы аккаунт, с которого происходит парсинг сам состоял в этой группе. Тогда парсер достанет эти группы из клиента Телеграмма и покажет их в меню. 

![pars](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/1a809561-0977-4aa8-b49d-7912dfa7b383)

Выбрав группу цифрой, начнётся парсинг, в директории парсера появится файл ```participants.txt```. В нём будут юзернеймы участников чата, которые можно попытаться заинвайтить. С "@" вначале и каждый в своей строке. 

__*Внимание!*__ *спарсить можно только тех участников, которые выставили себе юзернейм в настрйоках Телеграмма*

После этого можно перезапустить парсер и в меню выбрать инвайтинг. Инвайтер откроет ранее созданный ```participants.txt``` внесёт содержимое файла в список и поёдет по порядку пытаясь хоть кого-нибудь заинвайтить. У телеграмма очень умные алгоритмы. Пользуясь инвайтером для добавления людей в свою группу, есть риск попадания группы в теневой бан. Распознать теневой бан можно по тому, что в группу приходят сообщения об инвайте, но кол-во участников чата не увеличивается. Это не проблема инвайтера, это жестокие ограничения Телеграмма. __Рекомендую сделать аккаунт для инвайта админом группы, куда производится инвайт и добавлять не более 20 участников в день. Для сведения риска теневого бана к миниммуму, в парсере реализована рандомная задержка инвайта и ограничение на 20 попыток добавления за один запуск программы.__ В терминал будет выводиться юзернейм, если инвайт прошёл успешно и будет выводить подробное сообщение о ошибке если таковая случится.

__Датс олл. Пишите мне в телеграмм ```@DonMinionAmerimaChesburger```, если захотите поговорить или поблагодарить. Надеюсь вам понравится мой парсер.__

![Watermark](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/526fb03e-0921-4baf-8e8d-6f0cee8a9002)

