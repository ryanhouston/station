# Station

Station is a _most triumphant_ Ansible based declarative configuration for my
work**station**(s).

![Station](https://static.wikia.nocookie.net/billandted/images/8/8c/Station_II.jpg)

It's aim is to _be excellent to each other_ in order to document the tools I
consistently use on my workstation with configuration as code.

_Party on, dudes!_

![Bill & Ted](https://static01.nyt.com/images/2020/08/31/us/31xpbillted/31xpbillted-jumbo-v2.jpg)

## Setting up the Station

Install ansible on your system. On a Debian base system I use

`sudo apt install ansible-core`

Just installing `sudo apt install ansible` had issues with using the community
based modules.

There is a `debug.yml` playbook that will ensure ansible is working and print
out the current OS distribution and version.

```sh
ansible-playbook debug.yml`
```

First install any requirements from ansible galaxy collections.

```sh
ansible-galaxy install -r requirements.yml`
```

The following command is idempotent and will ensure the current system is in
sync with the station config.

```sh
ansible-playbook --ask-become-pass station.yml`
```

> [!WARNING] If fingerprint reader authentication is enabled you may experience
> ansible hanging when running commands. If this happens, disable fingerprint
> authentication temporarily with `sudo pam-auth-update --disable fingerprint`
> and re-enable it later with `sudo pam-auth-update --enable fingerprint`.
