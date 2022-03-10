# shutdown
As the command implies, this cmd shutdown the system. We can pass some parameters, options and messages with it.

Command Format:
```bash
shutdown [OPTION] [TIME] [MESSAGE] 
```
<br>

`time` - number of minutes. After those minutes system will shutdown. The `shutdown` cmd will power-off system in 1 minutes (default). We can add or reduce the time by passing time with it.
Example:
- `shutdown now` - will power-off system without any delay. (now = +0)
- `shutdown +10` - will power-off system 10 minutes later.
- `shutdown -r 17:30` - will reboot system at 5:30 PM.
<br>


we can send a message about the action to other user in the same system.
Example:
- `shutdown 'Sample Message...'`
- `shutdown --no-wall` - will not send wall message to other user about reboot.
<br>

### Options
- `-h` - halt system. (same as power off)
- `-r` - Reboot system
- `-P` - power off
- `-c` - cancel pending reboot
<br>


