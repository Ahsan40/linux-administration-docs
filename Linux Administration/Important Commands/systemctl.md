# systemctl
This command is used to control all units that are running by systemd.

`systemctl` - shows all the running units.

Command format:
```bash
systemctl [OPTION][TARGET]
```

### Options
- `status` - shows the status of the target
- `stop`  - stops the target
- `start` - starts the target
- `enable` - enables a target
- `disable` - disables a target
- `isolate` - changes the run level
- `set-default`  - change default run level

Example: 
```bash
sudo systemctl stop sound.target
```
After executing this command sound card will be stopped and sound will not work in the system. We can start it with `start` option as well.


Example (Run level):
```bash
sudo systemctl enable multi-user.target
sudo systemctl `set-default` multi-user.target
```

It will change the default run level of systemd to multi-user. In this way all the other run level can be used as well.