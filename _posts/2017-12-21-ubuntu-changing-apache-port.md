---
layout:       post
permalink:    ubuntu-changing-apache-port
title:        Changing Apache2's Default Port
heading:      A asdhajs dghajsdghjagsdh
extract:      qweqwe uqwe qyweuy quywet uqytweuy qtweuyt quewtuqytw eqtweuy tquywetuyqwt euytqwe tqwuyet qtweuy tquywet qtweuyq tweuy tquywet uqe. A g ahdgshjasgdjh agsjdhg ajhsdgjha gsdjhag sjdgajhsgdjha gdjhagsd gajhsdg jagsdhj gasjdhg ahsdg jahsgdja gdsjh agsdj gajhsdg asdg ahjsdgj agsd.
---

To change the port Apache2 listens on:
{% highlight text %}
cd /etc/apache2
cp ports.conf ports.conf.orig
sudo nano ports.conf
{% endhighlight %}

Change the `Listen` entry from the default **port 80** to the new port number, in this case **8181**:
{% highlight text %}
Listen 8181
{% endhighlight %}

Save and exit nano (**ctrl+o**, **ctrl+x**). Next, update the available sites to listen on the new port:
{% highlight text %}
cd /etc/apache2/sites-available
sudo nano 000-default.conf
{% endhighlight %}

Change the port number in the `VirtualHost` directive to use the new port number:
{% highlight text %}
<VirtualHost *:8181>
...
{% endhighlight %}

Now restart Apache:
{% highlight text %}
sudo systemctl restart apache2
{% endhighlight %}

Test using a browser or `curl`, using both the address and new port number:
{% highlight text %}
http://127.0.0.1:8181
{% endhighlight %}