# stress-ng snap

This is a snap packaging of [stress-ng](https://github.com/ColinIanKing/stress-ng), a tool to load and stress a computer.

## Install

This snap is available under [developer mode confinement](https://snapcraft.io/docs/install-modes#heading--devmode).
This is because `stress-ng` is a testing tool that needs a wide range of access to the system.
Keep in mind that snaps installed in developer mode don't upgrade automatically like [strictly confined and classic snaps](https://snapcraft.io/docs/snap-confinement).
The snap should be removed after testing or [updated manually](#update).

Because of its confinement mode, this snap is only available in the `latest/beta` and `latest/edge` [channels](https://snapcraft.io/docs/channels).
The most stable revision can be installed with:
```bash
sudo snap install stress-ng-dev --devmode --beta
```

The stress-ng command should now be available from the snap's namespace:
```console
$ which stress-ng-dev.stress-ng 
/snap/bin/stress-ng-dev.stress-ng
```

### Add alias
You can add an [alias](https://snapcraft.io/docs/commands-and-aliases) to run the program without the namespace. For example:
```console
$ sudo snap alias stress-ng-dev.stress-ng stress-ng
Added:
  - stress-ng-dev.stress-ng as stress-ng

$ which stress-ng
/snap/bin/stress-ng
```

> [!NOTE]
> If the alias matches the command installed with deb package, the application from the deb may be found first.
> This depends on the order of directories listed in the `PATH` environment variable.

## Update

To manually update the snap, use:

```bash
sudo snap refresh stress-ng-dev --devmode
```

## Use

For usage instructions refer to:

- [Ubuntu Wiki page about stress-ng](https://wiki.ubuntu.com/Kernel/Reference/stress-ng)
- [Ubuntu Man page](https://manpages.ubuntu.com/manpages/noble/man1/stress-ng.1.html)

### Local Build

Build it using [Snapcraft](https://snapcraft.io/snapcraft):

```bash
snapcraft -v
```

Then, install it in [devmode](https://snapcraft.io/docs/install-modes#heading--devmode):

```bash
sudo snap install --devmode *.snap
```
