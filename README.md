# weejoin

Weechat script to push notifications to Join. Based on weebullet by Lefty, located at https://github.com/LeftyBC/weebullet.

Requires an API key from http://joaoapps.com/join and a recentish version of Weechat with Python support enabled.

### Setup
- Place `weejoin.py` in `~/.weechat/python`
- To autoload weejoin on weechat's startup add `weejoin.py` to `~/.weechat/python/autoload`
- `/script load weejoin.py` (or `/python load weejoin.py` for newer weechats)
- `/set plugins.var.python.weejoin.api_key YOUR_API_KEY`
- Enjoy!

### Additional commands
`/send_push_note`  - sends a push manually from weechat

`/weejoin` - without arguments, prints a help message

`/weejoin listdevices` - retrieves a list of your pushable devices and their nicknames

`/weejoin listignores` - retrieves a list of ignored channels

`/weejoin ignore` - ignores a given channel or channels

`/weejoin unignore` - unignores a given channel or channels

### Optional settings
`/set plugins.var.python.weejoin.away_only [0|1]` set to `0` if you wish to always receive notifications, or only when you are marked away (default `1`)

`/set plugins.var.python.weejoin.inactive_only [0|1]` set to `0` to receive notifications for your active buffer, or `1` to skip notifications for the active buffer (default `1`)

`/set plugins.var.python.weejoin.device_iden [DEVICE_ID|all]` if you wish to be notified only on a specific device, or on all devices (default `all`)

`/set plugins.var.python.weejoin.ignored_channels [#channel1[, #channel2[, #channel3[, ...]]]]` if you wish to set ignored channels manually (default blank)

`/set plugins.var.python.weejoin.min_notify_interval [0|NUMBER]` to set a minimum interval in seconds between notifications (default 0, disabled)

`/set plugins.var.python.weejoin.ignore_on_relay [0|1]` set to 1 if you want to suppress push notifications when a client is connected to your weechat via weechat-relay (default `0`)
