# Sysinfo

> Author: Brian Tomlinson <darthlukan@gmail.com>


## Description

> A simple Python 3 script that sends system information to STDOUT.  It is meant to be used by docks and statusbars
> commonly used in Window Manager-only setups, such as lemonbar, i3bar, pypanel, etc.  Just call this script in your
> bar's config.  The script does not have a timer, it leaves that up to the calling handler.


## Screenshot

> Here's an example of sysinfo.py running as the status_command in i3's bar:

![i3bar example](example_i3bar.png)


## Usage

> Sysinfo is able to read command line flags, which is nice for testing the output prior to loading it into a bar/panel.

> Examples:

```
    $ ./sysinfo.py -d / /home -c 1 -m 1
    >> DISKS( /: 31.39/110.66GB /home: 761.09/901.02GB ) | CPU: 0.0% | RAM: 3.96/15.36GB | 2015-08-30 17:01:06 |

    $ ./sysinfo.py -l 1
    >> LOAD: 0.81, 0.6, 0.5 | 2015-08-30 17:03:29 |

    $ ./sysinfo.py -d / /home -c 1 -m 1 -l 1 -dt '%Y-%m-%d'
    >> DISKS( /: 31.40/110.66GB /home: 761.09/901.02GB ) | CPU: 0.0% | RAM: 3.95/15.36GB | LOAD: 0.34, 0.5, 0.47 | 2015-08-30 |
```

> As you can see, by default, so long as at least one argument is passed to the script, a datetime is generated and
> returned as the last portion of the string (since the default for most users is to place this information as the
> right-most item next to the systray).  The ```-dt``` and ```--date-time``` arguments are synonymous and follow the
> same rules as the [Python strftime directives](http://strftime.org).

> The other arguments are simple booleans, so long as there is a value after the flag the argparse library will assume
> the value is "True." If you do not wish to see an item of information, then omit the corresponding flag, with the
> exception of the date-time argument, that one will always appear unless the script is called empty of arguments, in
> which case the help documentation will be displayed.


## Dependencies

> The only external dependency is [psutil](https://github.com/giampaolo/psutil)


## Compatibility

> This script should work by default on any system supported by psutil, even Windows, though the usecase is fairly
> linux specific.


## License

> WTFPL, see LICENSE file.
