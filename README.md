# Sysinfo

> Author: Brian Tomlinson <darthlukan@gmail.com>


## Description

> A simple Python 3 script that sends system information to STDOUT.  It is meant to be used by docks and statusbars
> commonly used in Window Manager-only setups, such as lemonbar, i3bar, pypanel, etc.  Just call this script in your
> bar's config.  The script does not have a timer, it leaves that up to the calling handler.


## Screenshot

> Here's an example of sysinfo.py running as the status_command in i3's bar:

![i3bar example](example_i3bar.png)


## Dependencies

> The only external dependency is [psutil](https://github.com/giampaolo/psutil)


## Compatibility

> This script should work by default on any system supported by psutil, even Windows, though the usecase is fairly
> linux specific.


## License

> WTFPL, see LICENSE file.
