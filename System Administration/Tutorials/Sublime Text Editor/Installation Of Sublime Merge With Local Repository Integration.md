### To Purchase Sublime Merge Follow The Link Shown Below
---
[Sublime Merge Purchase Link](https://www.sublimehq.com/store/merge)

# Linux Package Manager Repositories

Sublime Merge includes an auto-upgrade mechanism on Windows and OS X to make upgrades a snap. Instead of going against the grain of the Linux ecosystem, packages and package repositories are provided for most of the major distributions.

Builds listed in the dev channel are only available to licensed users. Users who are evaluating Sublime Merge before purchase will need to use the stable channel.

- [apt](https://www.sublimemerge.com/docs/linux_repositories#apt) - _Ubuntu, Debian_
- [pacman](https://www.sublimemerge.com/docs/linux_repositories#pacman) - _Arch_
- [yum](https://www.sublimemerge.com/docs/linux_repositories#yum) - _CentOS_
- [dnf](https://www.sublimemerge.com/docs/linux_repositories#dnf) - _Fedora_
- [zypper](https://www.sublimemerge.com/docs/linux_repositories#zypper) - _openSUSE_

## apt

The apt repository contains packages for both x86-64 and arm64.

Install the GPG key:

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/sublimehq-archive.gpg > /dev/null
```

Ensure apt is set up to work with https sources:

```
sudo apt-get install apt-transport-https
```

Select the channel to use:

Stable

```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

Dev

```
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

Update apt sources and install Sublime Merge

```
sudo apt-get update
sudo apt-get install sublime-merge
```