---
layout: post
title:  "Clientlibs"
permalink: /clientlibs/
---
![image tooltip here](/assets/img/cl1.png)<br><br>

<b>Steps To Create Clientlibs</b><br>

<b>Step 1</b>:Create new custom component inside apps/projects_name/components/content and give it name as slideshow<br>
<b>Step 2</b>:Change slideshow.jsp to slideshow.html as we are creating HTL component.<br>
<b>Step 3</b>:Create new node inside slideshow component with type cq:ClientLibraryFolder and name clientlibs<br>
<b>Step 4</b>:Add new property called categories of type string array so select multi and project_name.components.slideshow<br>
<b>Step 5</b>:Add js.txt and css.txt and add the following code<br>
<i>js.txt</i><br>
{% highlight ruby %}
#base=js
slideshow.js
{% endhighlight %}
<br>
<i>css.txt</i><br>
{% highlight ruby %}
#base=css
slideshow.css
{% endhighlight %}
<br>
<b>Step 6</b>:Create js and css folder and add slideshow.js and slideshow.css respectively<br>
<b>Step 7</b>:Add below code-
<i>slideshow.html</i><br>
{% highlight ruby %}
<!-- Slideshow container -->
<div class="slideshow-container">  

  <!-- Full-width images with number and caption text -->
  <div class="mySlides fade">
    <div class="numbertext">1 / 3</div>
    <img src="/content/dam/we-retail/en/people/mens/men_1.jpg" style="width:100%">
    <div class="text">Caption Text</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">2 / 3</div>
    <img src="/content/dam/we-retail/en/people/mens/men_4.jpg" style="width:100%">
    <div class="text">Caption Two</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">3 / 3</div>
    <div data-sly-use.pathjs="imagePath.js" />
        <img src="${pathjs.path}" style="width:100%">
    <div class="text">Caption Three</div>
  </div>

  <!-- Next and previous buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>
<br>

<!-- The dots/circles -->
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span> 
  <span class="dot" onclick="currentSlide(2)"></span> 
  <span class="dot" onclick="currentSlide(3)"></span> 
</div>
<sly data-sly-use.clientlib="/libs/granite/sightly/templates/clientlib.html" />
<sly data-sly-call="${clientlib.css @ categories='blog.components.slideshow'}" /> 
<sly data-sly-call="${clientlib.js @ categories='blog.components.slideshow'}" />
{% endhighlight %}
<br>
<i>slideshow.js</i><br>
{% highlight ruby %}
#var slideIndex = 0;
showSlides();

function showSlides() {
    var i;
    var slides = document.getElementsByClassName("mySlides");
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none"; 
    }
    slideIndex++;
    if (slideIndex > slides.length) {slideIndex = 1} 
    slides[slideIndex-1].style.display = "block"; 
    setTimeout(showSlides, 5000); // Change image every 2 seconds
}

{% endhighlight %}
<br>
<i>slideshow.css</i><br>
{% highlight ruby %}
* {box-sizing:border-box}

/* Slideshow container */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Hide the images by default */
.mySlides {
    display: none;
}

/* Next & previous buttons */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}

/* Fading animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}

@keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}

{% endhighlight %}

<b>ClientLibs Properties</b><br>

![image tooltip here](/assets/img/cl2.png)<br><br>
