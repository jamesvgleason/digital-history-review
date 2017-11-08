---
layout: single-col
title: Sample Essay
date: 2017-11-02
---

{% include jumbotron.html
  title="Essay Example"
  image="images/BirdsEye_1886.jpg"
  text="This is where you put your catchy subtitle.
" %}


*This page provides a bogus essay, beginning with a full bleed header image (a jumbotron!) to illustrate how to implement the various typographic features we're using. The gray boxes should show you exactly what code you need to use; copy and paste it into your own essay pages and adjust the attributes as you need to.*


**• In all of the below examples, make sure you take extreme care with your quotation marks and other coding symbols!**

**• DO NOT use double quotation marks `"` in your titles or captions. Single quotation marks `'` are fine.**


## Essay Metadata
All essays must have the following metadata at the top of the page, with the values customized to your own page. **Be sure you have the 3 hyphens `---` before and after your metadata on their own lines**. The top of your essay page should look like:

``` markdown
---
title: Simms Building
author: Fred Gibbs
css: gibbs.css
date: 2017-11-02
---
```


## Footnotes
All good historical essays (as you're writing) show what their sources are, which helps readers know that actual research underlies the essay.

To get a footnote to show up, there are two steps:

1) put `[^SOMETEXT]` in your essay where you want the superscript number to appear, and change SOMETEXT to some unique signifier related to the content of the note. In your markdown file, your text will look like:

```
Here's a sample sentence with a footnote at the end. [^source] Here is yet another sentence. [^another-source] The Simms building was remodeled in 2013. [^abqjournal-12-2014]  
```

2) put  `[^SOMETEXT]: Your footnote text` at the bottom of your essay.


```
[^source]: Your footnote text
[^another-source]: Text for another footnote.
[^abqjournal-12-2014]: [Albuquerque Journal, 12-5-2014](https://www.abqjournal.com/506289/simms-renovation-complete.html).
```

Viewed as a webpage, the code above will render as:

Here's a sample sentence with a footnote at the end. [^source] Here is yet another sentence. [^another-source] The Simms building was remodeled in 2013. [^abqjournal-12-2014] Notice the footnotes at the bottom of this page! Also note that the numbering happens automagically.

[^source]: Your footnote text
[^another-source]: Text for another footnote.
[^abqjournal-12-2014]: [Albuquerque Journal, 12-5-2014](https://www.abqjournal.com/506289/simms-renovation-complete.html).




## Jumbotron
To achieve a jumbotron header, use the following code on your page, and alter the image filename and text accordingly:

``` html
{%raw%}{% include jumbotron.html
title="Essay Example"
image="images/BirdsEye_1886.jpg"
text="This is where you put your catchy subtitle."
%} {%endraw%}
```


## Images
There is one basic way we will embed images in our essay files. Note that it is totally different from how you learned to do them in Markdown itself. This is because if we want to maintain consistency between images, like how the captions appear, we have to make sure we display all images exactly the same way.

### Standard Usage

{% include figure.html class="img-right" width="33%" caption="Centennial Hotel" src="images/centennial-hotel.jpg" %}

Fusce vulputate eleifend sapien. Vestibulum purus quam, scelerisque ut, mollis sed, nonummy id, metus. Nullam accumsan lorem in dui. Cras ultricies mi eu turpis hendrerit fringilla. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; In ac dui quis mi consectetuer lacinia. Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum.


To embed the image above, we use:
```
{%raw%}{% include figure.html
  class="img-right"
  width="33%"
  caption="Centennial Hotel"
  src="images/centennial-hotel.jpg"
%}{%endraw%}
```


### Use whatever width you want
You can alter the width of the image **as a percentage of our standard page width**. You can have them appear on the left, right, or center of the page.


{% include figure.html class="img-left" width="50%" src="images/centennial-hotel.jpg" caption="Obviously we need a 50% image somewhere."%}

Fusce vulputate eleifend sapien. Vestibulum purus quam, scelerisque ut, mollis sed, nonummy id, metus. Nullam accumsan lorem in dui. Cras ultricies mi eu turpis hendrerit fringilla.

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; In ac dui quis mi consectetuer lacinia. Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum.


To achieve the above half-width image, use:
```
{%raw%}{% include figure.html
class="img-left"
width="50%"
caption="Obviously we need a 50% image somewhere."
src="images/centennial-hotel.jpg"
%}{%endraw%}
```


Fusce vulputate eleifend sapien. Vestibulum purus quam, scelerisque ut, mollis sed, nonummy id, metus. Nullam accumsan lorem in dui. Cras ultricies mi eu turpis hendrerit fringilla. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; In ac dui quis mi consectetuer lacinia. Nam pretium turpis et arcu. Duis arcu tortor, suscipit eget, imperdiet nec, imperdiet iaculis, ipsum.

{% include figure.html class="img-center" width="100%" caption="Make sure your image is large enough to be 100% width or it will look grainy. See above."  src="images/centennial-hotel.jpg" %}

To achieve the above full-width (but not jumbotron) image, use:
{%raw%}
```
{% include figure.html
  class="img-center"
  width="100%"
  caption="Make sure your image is large enough to be 100% width or it will look grainy. See above."
  src="images/centennial-hotel.jpg" %}
```
{%endraw%}


### Juxtapose
It's easy to set up a slider to compare historic and contemporary photos. If you find a historic image from a vantage point that you can replicate, please take a modern photo so we can better illustrate the changes in the surrounding space.

{% include juxtapose.html
image1="/images/kimo-1928.jpg"
image2="/images/kimo-1938.jpg"
caption="These sliders are way more effective the more closely you line up the before and after images."
%}

Include the change-over-time-slider, we use

```
{%raw%}{% include juxtapose.html
image1="images/kimo-1928.jpg"
image2="images/kimo-1938.jpg"
caption="These sliders are way more effective the more closely you line up the before and after images."
%}{%endraw%}
```




## Pull Quotes

As part of our effort to highlight our most important ideas---even in the context of relatively short essays---we want to use pull quotes.

### Standard usage
{% include aside.html class="pullquote" text="
Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque." %}

Aenean vulputate eleifend tellus. Aenean leo ligula, porttitor eu, consequat vitae, eleifend ac, enim. Aliquam lorem ante, dapibus in, viverra quis, feugiat a, tellus. Phasellus viverra nulla ut metus varius laoreet. Quisque rutrum. Aenean imperdiet. Etiam ultricies nisi vel augue. Curabitur ullamcorper ultricies nisi. Nam eget dui. Etiam rhoncus.


To place a pull quote as above, we use:


```
{%raw%}{% include aside.html
  class="pullquote"
  text="Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque."
  %}{%endraw%}
```

### Full-width quotes
If you are quoting from a historical source, you might want to say more than can fit in a normal pull quote format. For those cases, you can use a full-width blackquote to highlight a particularly juice quotation.

{% include full-width.html class="pullquote" text="
Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce id purus. Ut varius tincidunt libero. Phasellus dolor. Maecenas vestibulum mollis diam. Pellentesque ut neque.
" %}

To achieve the above full width pull quote, use:
```
{%raw%}{% include full-width.html
  class="pullquote"
  text=" Vestibulum ante ipsum primis in faucibus orci luctus ..."
%}{%endraw%}
```

---

### References
