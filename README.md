# **OSM-Translate-TelegramBot**

This bot it designed to help translation of [OpenStreetMap](https://www.openstreetmap.org) location from English to any Regional Language.

## Tech

OSM-Translate-TelegramBot uses various python packages / open source projects to work properly:

* [Pandas] - pandas is an open source, library providing high-performance, easy-to-use data structures and data analysis tools for the Python.
* [SQLAlchemy] -  Python SQL toolkit and Object Relational Mapper that gives application developers the full power and flexibility of SQL.
* [pyTelegramBotAPI] - A simple, but extensible Python implementation for the [Telegram Bot API](https://core.telegram.org/bots/api).
* [PyYAML] - YAML parser and emitter for Python.


## Installation

Tested on python 3.* 
```sh
$ git clone https://github.com/Dineshkarthik/OSM-Translate-TelegramBot.git
$ cd OSM-Translate-TelegramBot
$ pip install -r requirements.txt
```

## Configuration 

     token: 'YOUR_BOT_TOKEN'
     input_csv: '/PATH/TO/YOUR/INPUT/INPUT.CSV'
     db_name: 'NAME_FOR_DB_TO_BE_GENERATED'

 - token  - Your Telegram Bot API Token, to get the token follow the instructions available [here](https://core.telegram.org/bots#6-botfather)
 - input_csv - Path to the input csv file, which contains the Locations to be translated.
	- The Input csv file should consists of the following `3 mandatory columns`
		- osm_id - OSM Node ID of the Location
		- name - Name of the Location to be translated
		- translation - Suggested Google or any other translation if available (But the column is mandatory)
 - db_name -  Name for the Sqlite db that will be generated.

## Execution
```sh
$ python populated_db.py 
$ python translate_bot.py
$ python export_db.py
```
* Running `populated_db.py` will generate a Sqlite DB and will seed it with data from the input csv file.
* Running `translate_bot.py` will start the Telegram Bot.  
* Runnign `export_db.py` will export translated data available in DB to a CSV file.

   [Pandas]: <http://pandas.pydata.org/>
   [SQLAlchemy]: <https://www.sqlalchemy.org/>
   [pyTelegramBotAPI]: <https://github.com/eternnoir/pyTelegramBotAPI>
   [PyYAML]: <https://pypi.python.org/pypi/PyYAML>