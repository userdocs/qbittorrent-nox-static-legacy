# qbittorrent-nox-static-legacy

The `qbittorrent-nox-static-legacy` is a fully static build of qBittorrent 4.3.9 and libtorrent v1.2 built with modern dependencies. Derived from the [qbittorrent-nox-static](https://github.com/userdocs/qbittorrent-nox-static) project.

|This project only builds against the `v1.2` branch of Libtorrent so there are no pre releases and everything can be accessed via the latest release URL/API.

## Install the latest release

🔵 [The latest release page](https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest) for the most current build

Or uses these commands for your arch:

### x86_64

```bash
mkdir -p ~/bin && source ~/.profile
wget -qO ~/bin/qbittorrent-nox https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest/download/x86_64-qbittorrent-nox
chmod 700 ~/bin/qbittorrent-nox
```

### armhf (armv6)

```bash
mkdir -p ~/bin && source ~/.profile
wget -qO ~/bin/qbittorrent-nox https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest/download/armhf-qbittorrent-nox
chmod 700 ~/bin/qbittorrent-nox
```

### armv7

```bash
mkdir -p ~/bin && source ~/.profile
wget -qO ~/bin/qbittorrent-nox https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest/download/armv7-qbittorrent-nox
chmod 700 ~/bin/qbittorrent-nox
```

### aarch64

```bash
mkdir -p ~/bin && source ~/.profile
wget -qO ~/bin/qbittorrent-nox https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest/download/aarch64-qbittorrent-nox
chmod 700 ~/bin/qbittorrent-nox
```

## Revisions

The build has 5 main dependencies tracked that will trigger a rebuild on an update being available.

-  qBittorrent
-  Libtorrent
-  Qt
-  Boost
-  Openssl

When a new build is triggered for updating `Libtorrent` a new release will be generated as the release tags will be updated.

Since I do not append revision info to tags `Qt` - `Boost` - `Openssl` builds will only update the existing release assets.

To track these revisions you can use this command. All new releases start at a revision of `0` and increment by `1` per revised build.

```bash
jq -r '.revision' < <(curl -sL "https://github.com/userdocs/qbittorrent-nox-static-legacy/releases/latest/download/dependency-version.json")
```

Testing
