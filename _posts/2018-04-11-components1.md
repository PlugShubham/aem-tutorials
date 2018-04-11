---
layout: post
title:  "Design Dialog and Overlays"
permalink: /components2/
---
Design Dialog provide design configurations of the component. Accessible only in design mode. Not in editable mode. 
<br>
1. Touch UI<br>
2. Classic UI<br>

Follow below images to create Design Dialog: <br>

{% highlight ruby %}
Note: For cq:design_dialog sling:resouceType - cq/gui/components/authoring/dialog 
{% endhighlight %}

<b>Creating Design Dialog Boxes</b><br>

<b>Step 1</b><br><br>
<img src="{{ site.baseurl }}/assets/img/dd1.png"/><br><br>
<b>Step 2</b><br><br>
<img src="{{ site.baseurl }}/assets/img/dd2.png"/><br><br>
<b>Step 3</b><br><br>
<img src="{{ site.baseurl }}/assets/img/dd3.png"/><br><br>
<b>Step 4</b><br><br>
<img src="{{ site.baseurl }}/assets/img/dd4.png"/><br><br>


<b>Overlays and String Merger</b><br>

<img src="{{ site.baseurl }}/assets/img/overlay.png"/><br><br>

<i>Example 1</i>

{% highlight ruby %}
Libs ->sling->servlet->errorHandler -> right click -> create overlay -> match case ->

This will create similar structure in Apps folder

Create 404.html and add sample html
{% endhighlight %}

<br>

<i>Example 2</i>

{% highlight ruby %}
libs -> wcm -> foundation ->component -> text and image

create new components and add the above path as super type
{% endhighlight %}

<br>


<b>Core Components</b><br>

<img src="{{ site.baseurl }}/assets/img/core.png"/><br><br>

<i>Example</i>

{% highlight ruby %}
/apps/core/wcm/components

Copy address of core component and paste in new component that are created
in training. Copy list.html and place in training folder component

{% endhighlight %}