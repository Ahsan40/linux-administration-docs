# udev
It's the device manager of the kernel. It provides the low level access to the linux device tree. It also handles user space events when hardware added or removed from the system including loading firmware.

NOTE: Linux provides access to udev by providing a temporary file system named **tempfs** and it mounts to `/dev` on system startup.


udev config file is located at `/etc/udev`. There are a folder named `rules.d` which contains some `.rules` files. We can set some rules like what to do when a device mounted or ejected.


# dbus
It's an inter-process communication mechanism or a frameworks that allows processes to talk to each other securely and reliably. It also provides high level Object Oriented Programming interface.


# sysfs
It's a virtual file system provided by the linux kernel. It's presents info about various kernel subsystems such as Hardware Devices, Drivers etc. It's mounted to `/sys` dir.


# procfs
It's similar to sysfs  but it presents info about processes and other system info from kernel. It's located at `/proc`. The parameters that has been given at the boot time are also stored here in some files. We can use `cat` command to check that eg.  `cat cmdline`.

