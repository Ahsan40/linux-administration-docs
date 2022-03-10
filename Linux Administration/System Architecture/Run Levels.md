# Run Levels
There are total 7 run level from 0 to 6. This determine what to load when system init happens. Normally this happens automatically but we can manually configure it as we like.


- 0 -> Halt or shutdown system
- 1 -> Single user mode (safe mode - loads less program)
- 2 ->  multi-user mode without networking
- 3 -> Normal boot/Multi-user mode with networking
- 4 -> Unused/Customizable
- 5 -> Run level 3 with GUI Display Manager
- 6 -> Reboot
<br>

Run level are configured using one of this two method `systemd` or `systemv`. `systemd` is newer and optimized version of `systemv` with some new features but there are still some older system that uses `systemv` to this date.
<br>

# systemv
systemv used to use a file called `inittab` which located at `/etc/inittab`. It kind of looked like this,
![9cdf5dab59ecec2a8e24f70736167376.png](../../_resources/9cdf5dab59ecec2a8e24f70736167376.png)


And with this system know which run level to boot to. run levels are located at `/etc`. There are some folders named `rc0.d`, `rc1.d` etc. up to `rc6.d` and one additional `rc$.d`. Each of the `rc` folder contains scripts that will run on that corresponded run level. However, the scripts that `rc$.d` contains will run for all run level.

<center>

![dfb6aa2cf72799ea5243306aad1fb660.png](../../_resources/dfb6aa2cf72799ea5243306aad1fb660.png)
</center>

If we open any of the folder discussed above we will be able to see some file. Files that starts with `K` means kill and the number right after K like `K0`, `K01` etc are indicating the serial. We will see this normally at run level 0 and run level 6.
<center>

![0d1c26e636f4e80b9bed3466fe208581.png](../../_resources/0d1c26e636f4e80b9bed3466fe208581.png)
</center>
<br>

# systemd
It's located at `/etc/systemd`. It contains two types of scripts.
1.  System Scripts (`/etc/systemd/system`)
2.  Package Scrips (`/usr/lib/systemd/system`)

System scripts take precedence over package scripts.  Systemd also has a concept called targets.

## Targets
It's serves the same purpose as the run level but act little differently. Each target is named instead of numbered and is intended to serve a specific purpose. Where in systemv there were folder called `rc6.d` it's called here `reboot.target`. Some targets are implemented by inheriting all of the services of another target and adding additional services to it.
<center>

![5a8ff003d7ab05e1dedd93884c6a0b89.png](../../_resources/5a8ff003d7ab05e1dedd93884c6a0b89.png)
</center>
<br>
<br>

Example of `systemd` script for apache web server,
<center>

![c59ecf355b2357fd1a53d7e8de36a43f.png](../../_resources/c59ecf355b2357fd1a53d7e8de36a43f.png)
</center>

Same script for `systemv`
<center>

![66c1168f4bd294aa530acae9dfc9d9dc.png](../../_resources/66c1168f4bd294aa530acae9dfc9d9dc.png)
</center>