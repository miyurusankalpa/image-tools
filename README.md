Scaleway's images - Toolbox
===========================

This repository contains the scripts used to boot an image on [Online.net's cloud services](http://labs.online.net/).
Scripts are built-in official images and some of them are also used in the official Initrd image.

It is planned to to create packages (.deb) for distributions.

Why this repository exists ?
----------------------------

Because we create more and more images, and they have lots of common files, so we categorize the kind of files (flavors) and try to prevent duplicates files and issues accross similar images

---

The official images built with [image-tools](https://github.com/scaleway/image-tools) are using this repositoty.

Non-exhaustive list :

- [Ubuntu](https://github.com/scaleway/image-ubuntu) (with FLAVORS=common,upstart,docker-based)
- [Debian](https://github.com/scaleway/image-debian) (with FLAVORS=common,sysvinit,docker-based)
- [ArchLinux](https://github.com/scaleway/image-archlinux) (with FLAVORS=common,systemd,docker-based)
- [OpenSuse](https://github.com/scaleway/image-opensuse) (with FLAVORS=common,systemd,docker-based)
- [Fedora](https://github.com/scaleway/image-fedora) (with FLAVORS=common,systemd,docker-based)
- [Slackware](https://github.com/scaleway/image-slackware) (with FLAVORS=common,docker-based)
- [Alpine Linux](https://github.com/scaleway/image-alpine) (with FLAVORS=common,docker-based)
- [Docker app](https://github.com/scaleway/image-app-docker) (with FLAVORS=common,upstart,docker-based, by inheriting the Ubuntu image)
- ...

Upgrade a running image
-----------------------

```bash
wget -qO - http://j.mp/scw-skeleton | bash -e
```

Using flavors
-------------

```bash
# upstart
wget -qO - http://j.mp/scw-skeleton | FLAVORS=upstart bash -e
```

```bash
# sysvinit
wget -qO - http://j.mp/scw-skeleton | FLAVORS=sysvinit bash -e
```

Using branches
--------------

```bash
# flavor=upstart on branch=feature-xxx
wget -qO - http://j.mp/scw-skeleton | FLAVORS=upstart BRANCH=feature-xxx bash -e
```

Using curl
----------

```bash
curl -L -q http://j.mp/scw-skeleton | DL=curl bash -e
```

Alternative url
---------------

```bash
wget -qO - https://raw.githubusercontent.com/scaleway/image-tools/master/scripts/install.sh | ... bash -e
```

---

Misc commands
-------------

Run unit test suite

```bash
curl -L -q http://j.mp/scw-skeleton | bash && oc-image-unit
```

---

A project by [![Scaleway](https://avatars1.githubusercontent.com/u/5185491?v=3&s=42)](https://www.scaleway.com/)
