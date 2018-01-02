---
layout:       post
permalink:    ubuntu-server-virtualbox-guest-additions
title:        Installing VirtualBox Guest Additions on Ubuntu Server 17.10
heading:      A asdhajs dghajsdghjagsdh
extract:      qweqwe uqwe qyweuy quywet uqytweuy qtweuyt quewtuqytw eqtweuy tquywetuyqwt euytqwe tqwuyet qtweuy tquywet qtweuyq tweuy tquywet uqe. A g ahdgshjasgdjh agsjdhg ajhsdgjha gsdjhag sjdgajhsgdjha gdjhagsd gajhsdg jagsdhj gasjdhg ahsdg jahsgdja gdsjh agsdj gajhsdg asdg ahjsdgj agsd.
---

In order to use **VirtualBox shared folders** with **Ubuntu Server** first install **VirtualBox Guest Additions**. For this to work, a few additional modules are required:

{% highlight text %}
sudo apt install -y dkms build-essential linux-headers-generic linux-headers-$(uname -r)
{% endhighlight %}

Once the Linux headers have been installed, mount the Guest Additions CD and run:
{% highlight text %}
sudo mount /dev/cdrom /media/cdrom
sudo ./VboxLinuxAdditions.run
{% endhighlight %}

A warning about **X11** is shown, however rebooting shows any configured shared folders under `/media/sf_<folder name>`.