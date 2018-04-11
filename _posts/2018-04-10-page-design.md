---
layout: post
title:  "Page Design"
permalink: /pagedesign/
---
Page Design is used to declare clientlibs for complete page which you can use on both page level
and template level.
<br>

Follow below images to create Page Design: <br>

{% highlight ruby %}
Tools->operation-> configuration

Designs -> New ->create Page->project_name

Design node is created in etc design folder
{% endhighlight %}
<br>
<img src="{{ site.baseurl }}/assets/img/pd1.png"/><br>
<b>Give category as project_name.site.design and add clientlibs files as shown in [clientlibs][clientlibs] Page.</b><br><br>
{% highlight ruby %}
Properties of page -> advanced- > design 
{% endhighlight %}
<br>
<img src="{{ site.baseurl }}/assets/img/pd2.png"/><br>
<b>Give path till clientlibs-site</b><br><br>
<b>For adding the page design at Template level</b><br>
{% highlight ruby %}
Goto edit template -> page design
{% endhighlight %}
<br>
<img src="{{ site.baseurl }}/assets/img/pd3.png"/><br><br>


[clientlibs]:{{ site.baseurl }}/clientlibs