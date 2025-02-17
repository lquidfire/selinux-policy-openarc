# SELinux policy for OpenARC

This SELinux policy is being made ready for merging with the SELinux RefPolicy.

I have created a separate Branch with a policy version that will work on AlmaLinux 9.5+ (and similary OS's).

## Dependencies

In order to build this SELinux policy, you will need:

* policycoreutils-devel
* make
* m4
* python3
* policycoreutils-python-utils

### DNF-based systems

```
# dnf install policycoreutils-devel
```

### Debian / Ubuntu

```
# apt install build-essential policycoreutils-dev policycoreutils-python-utils
```

## Installation

Installation follows the standard SELinux module building process.

Clone this repository to somewhere on your system.

Once that is done:

```
# make -f /usr/share/selinux/devel/Makefile arc.pp
...
Compiling targeted narc module
Creating targeted arc.pp policy package
rm tmp/arc.mod.fc tmp/arc.mod
# semodule -i arc.pp
```
If you install this SELinux policy after `openarc` has been installed and set up, remember to run `restorecon -v ...` on all `openarc` directories and files.
