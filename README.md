THIS PROJECT IS DEPRECATED
============

s(uper)-uzzbot (telegram-bot)
============

A Telegram Bot based on plugins using [tg](https://github.com/Rondoozle/tg). Forked from [uziins' uzzbot](https://github.com/uziins/uzzbot), which is forked from [Yagop's](https://github.com/yagop/telegram-bot).

[Installation](https://github.com/yagop/telegram-bot/wiki/Installation)
------------
```bash
# Tested on Debian 7, for other OSes check out https://github.com/yagop/telegram-bot/wiki/Installation
sudo apt-get install libreadline-dev libconfig-dev libssl-dev lua5.2 liblua5.2-dev libevent-dev make unzip git redis-server g++ libjansson-dev libpython-dev expat libexpat1-dev
```

```bash
# After installing the dependencies, install the bot
cd $HOME
git clone https://github.com/LucentW/s-uzzbot.git
cd s-uzzbot
./launch.sh install
./launch.sh # Will ask you for a phone number & confirmation code or just your bot token.
```

There are two more scripts to launch the bot: `launchd.sh` will run tg-cli over gdb, `launchf.sh` will take care of restarting the bot in case it crashes, deleting tg-cli's `state` file to prevent reparsing buggy/broken messages.

To enable the API bot mode, before doing `./launch.sh install`, run `touch bot_mode`.

Take in account that logging in with a bot token has some caveats: `delmsg` and `mute` do not work (API bots cannot delete messages), by reply commands such as `#promote` might misbehave, `!join` will not work (API bots can only be invited, they cannot join a group by themselves).

Enable more [`plugins`](https://github.com/LucentW/s-uzzbot/tree/master/plugins)
-------------
See the plugins list with `!plugins` command.

Enable a disabled plugin by `!plugins enable [name]`.

Disable an enabled plugin by `!plugins disable [name]`.

Those commands require a privileged user, privileged users are defined inside `data/config.lua` (generated by the bot), stop the bot and edit if necessary.


Run it as a daemon
------------
If your Linux/Unix comes with [upstart](http://upstart.ubuntu.com/) you can run the bot by this way
```bash
$ sed -i "s/yourusername/$(whoami)/g" etc/uzzbot.conf
$ sed -i "s_telegrambotpath_$(pwd)_g" etc/uzzbot.conf
$ sudo cp etc/uzzbot.conf /etc/init/
$ sudo start uzzbot # To start it
$ sudo stop uzzbot # To stop it
```


------------
Bots:

- [@Akuma95](https://telegram.me/Akuma_95) [DEPRECATED]
- [@Akuma95_Bot](https://telegram.me/Akuma95_bot) (API Version)[DEPRECATED]

