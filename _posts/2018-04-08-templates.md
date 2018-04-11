---
layout: post
title:  "Templates"
date:   2018-04-08
---

Used to create page in AEM. It defines structure content and components that can be used on page. 
Properties like allowedPath, allowedParents and AllowedChildren restricts the usage of templates

Two Types of Templates:

1.Static Templates - Created by developers and stored in apps folder. <br>
2.Editble Templates - Created by Authors and stored in conf folder. Create [Editable Template][Editable Template]

{% highlight ruby %}
Note: cq:templates tells which templates was used in the page
{% endhighlight %}
<br>
<b> CREATING STATIC TEMPLATE</b><br>

<b>Step 1</b>: Go to Select CRXDE Lite at http://localhost:4502/crx/de/index.jsp.
Inside apps folder create folder with name learner. Inside learner create folder
templates and components. Inside components create two more folder one with name 
content and other structure.<br>

<b>Step 2</b>:Right-click the template folder (within your application), select Create, Create Template.

<img src="{{ site.baseurl }}/assets/img/step1.png"/>

<br>
<b>Step 3</b>:Enter the following information into the Create Template dialog box:<br>

<b>Label</b>: The name of the template to create. Enter contentpage.<br> 
<b>Title</b>: The title that is assigned to the template. Enter Base Content Page.<br>
<b>Description</b>: The description that is assigned to the template.<br>
<b>Resource Type</b>: The component's path that is assigned to the template and copied to implementing pages. Enter /apps/learner/components/structure/contentpage.<br>
<b>Ranking</b>: The order (ascending) in which this template will appear in relation to other templates. Setting this value to 1 ensures that the template appears first in the list.<br>

<img src="{{ site.baseurl }}/assets/img/step2.png"/>
<br><br>
<b>Step 4</b>:Add a path to Allowed Paths. Click on the plus sign and enter the following value: /content(/.*)?.
<br><br>
<img src="{{ site.baseurl }}/assets/img/step3.png"/>
<br><br>
<b>Step 5</b>:Click Next for Allowed Parents.
<br>
<b>Step 6</b>:Select OK on Allowed Children.
<br>

DONE!!!!!

Click [Create contentpage component][Create contentpage component] 

[Editable Template]:{{ site.baseurl }}/etemplates
[Create contentpage component]:{{ site.baseurl }}/components