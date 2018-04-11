---
layout: post
title:  "Introduction to AEM"
date:   2018-04-08 12:07:16 +0530
permalink: /intro/
---
`AEM` page is instance of template and template decides which component are allowed within template.To create any page you have to
create template first. In  `resourceType` you can give the allowed component path. Once the template is created you need to check 
whether the resourceType component is present or not. If not we have to create component. To create component follow the steps provided
in the [components][components] link.<br>

<b>Deconstructing Creative design</b>

Suppose we have a URL - `http://localhost:4502/content/we-retail/language-masters/en.html` 
For deconstructing creative design the steps are given below:<br>

<b>Http Request</b>

<img src="{{ site.baseurl }}/assets/img/request.png"/>

<br>
<b>Wiki/sling - Content Resolution</b> content resolution is `/content/we-retail/language-masters/en`
<br>
<b>Get Resource Type</b>

<img src="{{ site.baseurl }}/assets/img/resource.png"/>

<br>
<b>Script Locations</b> Search for resource type in apps folder. If it is not in apps folder then search in libs folder. In apps folder
 we got `/apps/weretail/components/structure/page` Page component. 
 
<br>
<b>Script name</b> Search if page.html is there or not.
<br>
<b>Script</b> In this case it is not there then search it in SuperType component.

<img src="{{ site.baseurl }}/assets/img/super.png"/>

<br>
<b>Include Options</b> Every time request is sent, it first search in resourceType. If it is not present in resource type then
it will search in SuperType component.
<br>
{% highlight ruby %}
Note: apps folder got higher preference then libs in finding the script from resourceType`
{% endhighlight %}

[components]: {{ site.baseurl }}/components