---
layout: post
title:  "Components"
permalink: /components/
---

Components are re-usable modules that implement specific application logic to render the content of your web site. You can think of a component as a collection of scripts (for example, JSPs, Java servlets, and so on) that completely realize a specific function. In order to realize this functionality, it is your responsibility as a CQ developer to create scripts that perform specific functionality. For more information about components, see Components.

By default, a component has at least one default script, identical to the name of the component. To create a render component, perform these tasks:

1. Go to Select CRXDE Lite at http://localhost:4502/crx/de/index.jsp.<br>
2. Right-click /apps/project_name/components/structure, then select Create, Create Component.<br>
3. Enter the following information into the Create Component dialog box:<br>

<b>Label</b>: The name of the component to create.<br>
<b>Title</b>: The title that is assigned to the component.<br> 
<b>Description</b>: The description that is assigned to the template.<br> 
<b>Super Type</b>: Parent Component. In case you want to include properties of other component.<br>

4.In the Create Component dialog, Click OK. 

<b>Lets create one nav component.Change nav.jsp to nav.html</b><br>

<i>TopNav.java</i><br>

{% highlight ruby %}
package apps.blog.components.structure.nav;

import java.util.*;
import java.util.Iterator;
import com.day.cq.wcm.api.Page;
import com.day.cq.wcm.api.PageFilter;
import com.adobe.cq.sightly.WCMUsePojo;

public class TopNav extends WCMUsePojo{
    private List<Page> items = new ArrayList<Page>();
    private Page rootPage;
    
    @Override
    public void activate() throws Exception{
        rootPage = getCurrentPage().getAbsoluteParent(2);
        
        if(rootPage == null){
            rootPage = getCurrentPage();
        }
        Iterator<Page> childPages = rootPage.listChildren(new PageFilter(getRequest()));
        while(childPages.hasNext()){
            items.add(childPages.next());
        }
        
    }
    
    public List<Page> getItems(){
        return items;
    }
    
    public Page getRoot(){
       return rootPage;
    }
}

{% endhighlight %}

<i>nav.html</i><br>

{% highlight ruby %}
<div class="topnav" data-sly-use.topnav="TopNav">
    <ul class="topnav">
        <li class="nav_home_fixed">
            <a class="nav_home_fixed" href="/content/blogs.html">Home</a>
        </li>
        <li class="topnav" data-sly-repeat="${topnav.items}">
            <a href="${item.path}">${item.title}</a>
        </li>
    </ul>
</div>
{% endhighlight %}

<i>rootpage.html</i>

{% highlight ruby %}
<div data-sly-use.jsobject="${'script.js' @value1='Welcome to Our Website'}" />
<div data-sly-resource="${@path='title',resourceType='/libs/wcm/foundation/components/title'}" />
<h2>${jsobject.message}</h2>
<div data-sly-use.logic="${'Logic' @value1='Shubham'}" />
${logic.message}  

<div data-sly-resource="${@path='nav',resourceType='/apps/blog/components/structure/nav'}" />

{% endhighlight %}
<br>

<b>Creating Dialog Boxes</b><br>

1.Create new node under tab1 with property cq:widgetCollection and name items.<br>
2.Create another node inside items with property cq:widget and add below properties<br>

![image tooltip here](/assets/img/comp1.png)<br>

<i>title.js</i>

{% highlight ruby %}

"use strict";

use(function(){
	var titleByAuthor = granite.resource.properties["titleProperty"];
    var pageName = currentPage.name;
    var jcrTitle = currentPage.title;

    var title = titleByAuthor || jcrTitle || pageName;

    return{
        title:title
    }

})

{% endhighlight %}

<i>title.html</i><br>

{% highlight ruby %}
<div data-sly-use.titlejs ="title.js">
    <h1 data-sly-element=${currentStyle.type}>${titlejs.title}</h1>
</div>
{% endhighlight %}

<br>

<b>Converting Classic Dialog to Touch UI Dialog Boxes</b><br>

1.Download conversion dialog zip and import package in package manager<br>
2.Tools -> conversion tools -> select your component > convert > done

