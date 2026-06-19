# telegram-parser -- Telegram Parser and Inviter

I'm archiving this repo. Telegram moderation has become stricter, making invites impossible and parsing difficult.
So please stop writing to me about the project's functionality.
I wrote the code a long time ago, at the very beginning of my career as a software engineer, and now I feel that it smells. It's another reason why I made a decision to archive this repo - I have no interest in circumventing the restrictions of this "messenger for scam".
If you want to try your luck at bypassing Telegram's algorithms, you can fork the project.
Bye for now.

# Updates
## v2.0
* __.session files can now be used for authentication. Store them into the directory__
* __Added the ability to parse UserIDs__
* __Added phone numbers -> .session converter__
  


## 1. Preparation
Before you begin, you need to find your API_ID and API_HASH tokens. Go to https://my.telegram.org/apps and log in. Select __API Development Tools__.

![12591615102022_5c20dcbcfbab07ab6c2df7e27444d5ac2afca569](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/75080769-1aa6-4cbc-ab75-cd0a1e04ec09)

In the next window, fill in the “App title” and “Short name” fields. Select “desktop”.

![gfbauf](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/963ca90a-b9f7-4f94-bc95-a87742742239)

Click “Create Application” and, in the window that appears, make a note of the API_ID and API_HASH. 
__The API_ID and API_HASH work with any account. You can use the API_ID and API_HASH from a third-party account.__
## 2. Environment Configuration
__Windows__
* Download Python 3.12 from https://www.python.org/ftp/python/3.12.0/python-3.12.0-amd64.exe
* __During installation, be sure to check the “Add to PATH” box__
  ![hgai](https://github.com/Keqy/telegram-parser-v1.0/assets/96333229/046ed050-5a00-4c94-8758-6de165e81ca3)
* Open the command prompt (press the “Win” key + the “R” key, then enter the command ```cmd```)
* Use the ```cd``` command to navigate to the parser directory. Example: ```cd C:Users/Keqy/programs/repos/telegram-parser-v2.0```
* Create a virtual environment with ```py -m venv venv```, then activate it with ```.\venv\Scripts\Activate```
* Install Telethon with ```pip install telethon```

__Linux__
* Open the terminal and update the packages with ```sudo apt update```
* Install Python and Git: ```sudo apt install python3 python3-pip git -y```
* Clone the repository: ```git clone https://github.com/Keqy/telegram-parser-v2.0/```
* ```cd``` into the parser directory.
* Create a virtual environment: ```py -m venv venv```, then activate it: ```.\venv\bin\Activate```


## 3. Usage
The parser settings will open the first time you run the program.

![image](https://github.com/Keqy/telegram-parser-v2.0/assets/96333229/b465cb54-843f-4fe2-94ed-c5e68836a923)

Enter your API_ID. __It contains only numbers. No spaces__

Enter your API_HASH. __API_HASH contains only numbers and letters of the Latin alphabet. No spaces__

Here, in steps 3 and 4, you can enable or disable the username/user ID parsing feature. By default, both are parsed.

__CONVERTER__

The converter is located in the settings under ```Add Userbot Account```. The Telegram account’s phone number is fed into the converter. A .session file is created in the project directory for quick userbot authorization. You can also add your own .session files to the root folder and use them for parsing or inviting users.

![image](https://github.com/Keqy/telegram-parser-v2.0/assets/96333229/9fc11349-ddf8-441e-a386-a301847a5942)

__The converter will not work if the API_ID or API_HASH is invalid or entered incorrectly__
__A new API_ID and API_HASH are __NOT__ required for each new account__

The settings are stored in ```options.txt``` in the project directory.
After configuring the settings, enter the Latin character ```e```. In the parser, this is used to exit.
After exiting the settings, the main menu will open.

![image](https://github.com/Keqy/telegram-parser-v2.0/assets/96333229/8a764eab-22db-429e-a900-514a78c3d46f)

### Parsing
In the parsing window, select the account that is a member of the groups you want to parse.

![image](https://github.com/Keqy/telegram-parser-v2.0/assets/96333229/00a72f59-f2d3-496b-80d8-63f9507f7a1b)

![image](https://github.com/Keqy/telegram-parser-v2.0/assets/96333229/56a17b94-fb7b-4e16-84ad-9ebc9f7b131a)

The matched usernames and user IDs will be stored in the directory in the files ```usernames.txt``` and ```userids.txt```.

### Inviting
In the invitation window, select an account that is a member of the group you want to invite. Then enter the group name.
