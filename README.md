Telegram Crypto Currency Bot
=====================

[![Python3](https://img.shields.io/badge/python-3.6-blue.svg)](https://github.com/Der-Eddy/discord_bot)

A simple crypto currency bot for [our justhold.de telegram group](https://www.justhold.de/) (or private chats!) based on [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) and the newest Python 3. The bot uses the [coinmarketcap.com API](https://coinmarketcap.com/api/) to obtain all data.


Commands List
-------------
Command | Discription | Usage
----------------|--------------|-------
`/btc`, `/sat` | Converts a given Satoshi or BTC amount to Ether | `/sat 10000`
`/eth` | Converts a given Ethereum amount to Bitcoin | `/eth 0.5`, `/eth 2.367`
`/coin` | Shows the current price of one given cryptocurrency. You can either use the symbol (i.e. `ETH`, `BTC`) or the full name | `/coin ethereum`, `/coin eth`
`/top` | Shows the current top crypto currency based on their market cap | `/top`
`/github` | Displays a link to the GitHub Repository | `/github`
`/coinflip` | Flips a coin | `/coinflip`, `/coinflip Kopf Zahl`
`/help` | Sends a link to the command list | `/help`

List to copy for [@BotFather](https://telegram.me/BotFather):

    sat - Converts a given Satoshi or BTC amount to Ether
    eth - Converts a given Ethereum amount to Bitcoin
    coin - Shows the current price of one given cryptocurrency
    top - Shows the current top crypto currency based on their market cap
    github - Displays a link to the GitHub Repository
    coinflip - Flips a coin
    help - Sends a link to the command list

Run
-------------
Either run it directly via `python3 main.py` or use systemd. An example for a systemd service can be found at `telegram.service.example`:

    [Unit]
    Description=Telegram Crypto Bot
    After=multi-user.target
    [Service]
    WorkingDirectory=/home/eddy/telegram_bot
    User=eddy
    Group=eddy
    ExecStart=/usr/bin/python3.6 /home/eddy/telegram_bot/main.py
    Type=idle
    Restart=on-failure
    RestartSec=15
    TimeoutStartSec=15

    [Install]
    WantedBy=multi-user.target


Settings
-------------
Copy `config.example.py` to `config.py` and add your Telegram API token from your bot. If you are in a weird country called Germany, you maybe want to change `__LOCALE_BILLION__` to `Mia.` instead.

    __TOKEN__ = 'tspOGQiAoEqdEEEBzinmhJg4VuvenEzKiH39NzsZQqDDq'
    __LOCALE_BILLION__ = 'bil.'
    __ADMINS__ = [369613251,]

Don't forget to allow groups at [@BotFather](https://telegram.me/BotFather) if you want to add the bot to groups.

List of requirements
-------------

    python>=3.6.0
    python-telegram-bot
    requests
    tzlocal

