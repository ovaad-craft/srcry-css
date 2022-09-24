<p align="center">
  <img src="logos/srcry_logo_a.svg" style="display: inline-block; width: 60%; min-width: 350px; margin: 0 auto;" />
</p>

<br /><br />

# Table Of Contents

[Intro](#intro)

[Setup](#setup)

[Size Libraries](#size-libraries)

[Box Size Library](#box-size-library)

[Text Size Library](#text-size-library)

[Line Size Library](#line-size-library)

[Configuration Classes](#configuration-classes)

[srcryBox Class](#srcrybox-class)

[baseSize](#basesize)

[crushGap](#crushgap)

[edgeChase](#edgechase)

[edgeChase](#edgechase)

[chaseStop](#chasestop)

[squishGrowth](#squishgrowth)

[stretchShrink](#stretchshrink)

[How To Use the srcryBox Class](#how-to-use-the-srcrybox-class)

[srcryTxt Class](#srcrytxt-class)

[text-size](#text-size)

[text-nudge-amt](#text-nudge-amt)

[kerning-nudge-amt](#kerning-nudge-amt)

[leading-nudge-amt](#leading-nudge-amt)

[Conclusion](#conclusion)

<br /><br />

# Intro
<p>
  When you consider how flexible our layouts need to be to adapt to all the devices that use the web, it’s safe to say Responsive Design has become somewhat of a form of animation programming in its’ own unique right.  Srcry (pronounced sorcery) is embracing this reality by introducing a means of behavioral scaling that allows developers to achieve more adaptable designs where it normally requires several media queries to come anywhere close to the same flexibility.
</p>

<p>
  Srcry differs from other frameworks by focusing on scaling and functionality rather than UI libraries and grid systems.  In total there’s 3 size libraries which are called <b><i>box size, text size</i></b> and <b><i>line size</i></b> as well as 2 configuaration classes called <b><i>srcryBox</i></b> and <b><i>srcryTxt</b></i> which make complex scaling extremely simple.  This is all done with pure CSS using custom variables and can be easily integrated into your existing code.
</p>

<p>
  What makes srcry the ultimate tool to add to your project is all the sizes are calculated based on the user’s screen and the golden ratio.  This makes your designs balanced and aesthetic right out of the box minimizing the need to tweak at settings to make things look and feel right.
</p>

<p>
  The golden ratio is present everywhere in nature and is what people instinctively judge by when deciding if a piece of artwork “looks good” or not.  If the portions of the artwork are consistent with the portions they commonly see used in the natural world, the creator of that artwork is deemed a “good artist” because they created something in the same fashion as if nature had done it itself which we intuitively know is a high level of mastery. Another benefit this provides is even in the event of a layout breaking on some device, it will do so in a way that’s proportionate with the golden ratio which will still look and feel right to the user while still being functional and accessible rather than wonky and distorted.
</p>
<br /><br /><br/>

# Setup
<p>
  Until this project becomes widely used enough to make available through a CDN you can just download the file and include it in your project then import it into your main CSS file as shown below.
  
  ```css
  @import url(path_to_folder/srcry.css);
  ```
  <br /><br /><br />
  
  # Size Libraries
  <br ><br />
  
</p>

## Box Size Library
<p>
  The <b><i>box size</i></b> library consists of 9 sizes which are <i><b>micro, xTiny, tiny, xSmall, small, loMed, hiMed, large</b></i> and <i><b>jumbo</b></i>.  Each size has a <b><i>scale</i></b> and <b><i>speed</i></b> setting to make them adaptable and relative to the screen which gives you a fine tuned yet flexible means of defining your elements.  It's best to regard a particular size as a range of multiple sizes rather than a static pixel size because what we consider large or small can vary from one device to another.  To keep things simple, there’s a syntax for using these box sizes which goes as follows.
</p>
<br />

```css
var(--[size]-[scale]-[speed])
```
<br />
<p>
  There are 2 scales and 11 speeds with 11 being the fastest so there’s not much to remember in order to use them.  So for example you could define the size of an element as shown below.
</p>
<br />

```css
.myClass{
  width:  var(--hiMed-2-7);
  height: var(--small-1-4);
}
```
<br />

<p>
  This may be all you need for your element to scale and behave the way you wish but this becomes more powerful when used with the <b><i>srcryBox</i></b> class which we’ll cover later on in this document.  There's a total of 198 scaling options and even though these sizes are adaptable they do have a set pixel size at their core which is shown in the table below.
</p>
<br />

  |srcryBox size|core pixel size|
  |:---:|:---:|
  |micro-1-1|4px|
  |micro-2-1|11px|
  |xTiny-1-1|18px|
  |xTiny-2-1|29px|
  |tiny-1-1|47px|
  |tiny-2-1|76px|
  |xSmall-1-1|97px|
  |xSmall-2-1|123px|
  |small-1-1|157px|
  |small-2-1|199px|
  |loMed-1-1|256px|
  |loMed-2-1|322px|
  |hiMed-1-1|521px|
  |hiMed-2-1|842px|
  |large-1-1|1077px|
  |large-2-1|1364px|
  |jumbo-1-1|1744px|
  |jumbo-2-1|2206px|

<br /><br />
## Text Size Library
<p>
  The text size library consists of 7 sizes that each have 5 speeds giving you a total of 35 scaling options to apply to your text. The 7 sizes are <b><i>caption, widget, article, subtitle, title, headline</b></i> and <b><i>jumbotron</i></b>.  The syntax for using the text size library goes as follows.

</p>
<br />

```css
var(--text-[size]-[speed])
```
<br />
<p>
  So if you wanted to use the <b><i>article</i></b> text on your element with a speed of 3 it would look like this.
</p>

<br />

```css
.myClass{
  font-size: var(--text-article-3);
}
```

<br /><br />
## Line Size Library
<p>
  The line size library consists of 11 sizes which are <b><i>fine, light, narrow, semiBold, bold, semiThick, thick, semiWide, wide, ultraWide</i></b> and <b><i>jumbo</i></b>.  There’s no scale or speed setting to these which makes them even simpler to use and the syntax goes as follows.
</p>
<br />

```css
var(--line-[size])
```

<br/>
<p>
  So if you want to add a <b><i>narrow</i></b> border to your element you would simply do the following.
</p>
<br />

```css
.myClass{
  border: var(--line-narrow) solid black;
}
```

<br />
<p>
  They even work well with defining box shadows which might look something like this.
</p>
<br />

```css
.myClass{
  border:     var(--line-narrow) solid black;
  box-shadow: 0 var(--line-semiBold) var(--line-thick) rgba(0, 0, 0, .65); 
}
```

<br /><br /><br />

# Configuration Classes
<p>
  The size libraries, though extremely useful on their own, are taken to the next level when used with the configuration classes.  The configuration classes consist of custom properties that tie into a series of algorithms that do all the tedious calculating required for scaling your elements.  As mentioned there’s only two which are called <b><i>srcryBox</i></b> and <b><i>srcryTxt</i></b> and all you have to do is add them to the class attribute of your HTML elements and define the custom properties in your own classes.
</p>
<br /><br />

## srcryBox Class
<p>
  The srcryBox class provides a family of custom properties for defining the scaling behavior of your elements.  These properties are called <b><i>crushGap, baseSize, edgeChase, chaseStop, squishGrowth</i></b> and <b><i>stretchShrink</i></b>.  Each property is available for both the width and height which can be specified simply by adding w or h at the end of the property.  When learning about the box size library you probably thought to yourself “what if I want the size of my element to be a size that’s somewhere in between two sizes?”.  Srcry resolves this by providing each property with two additional nudging properties called <b><i>nudge-slice</i></b> and <b><i>nudge-chunk</i></b> which are optional.  The <b><i>nudge-slice</i></b> is a very tiny portion that changes based on the size of the screen and a <b><i>nudge-chunk</i></b> is equivalent to 8 nudge slices.  In order to understand this further we need to cover the purpose of each property and how they’re to be used.
</p>
<br /><br />

#### baseSize
<p>
  The baseSize is the core size you want your element to be on the primary device you’re building your app or website to be used on.  This can vary from project to project so you need to judge for yourself what would be best to use.  If all else fails “mobile first” is a good rule of thumb to keep in mind.

#### crushGap
<p>
  The crushGap property applies to the size of the gap between the edges of your element and the edge of the screen rather than the size of your element.  This property kicks in when the screen is too small for the baseSize to fit to prevent breaking the layout.
</p>
<br />

#### edgeChase
<p>
  The edgeChase property is similar to crushGap except in regards to the amount of space there can be between the edge of the screen and the edges of the element before the element starts expanding to keep up with the screen.  So in other words, the element starts ignoring the baseSize setting to chase the edges of the screen.
</p>
<br />

#### chaseStop
<p>
  The chaseStop property defines the size your element can expand to before it stops chasing the edge of the screen.  You can look at this property like a second baseSize.
</p>
<br />

#### squishGrowth
<p>
  The squishGrowth property makes your HTML element expand as the screen size gets smaller rather than shrinking.  When applying it to the width the element will get wider as the height of the screen shrinks and when applied to the height the element will get taller as the width of the screen shrinks.  Due to the way this property works you need to define a <b><i>start</i></b>, <b><i>speed</i></b> and <b><i>max</i></b> property for it to come together.  The <b><i>start</i></b> property should be defined as a pixel size indicating the point at which the growth should begin as the screen gets smaller, so keep in mind that when a screen is smaller than this defined size this property will be active.  The <b><i>max</i></b> property is the maximum size the element should expand to so it doesn’t continue to grow out of hand.  The <b><i>speed</i></b> property defines how quickly the element should reach the maximum size defined. 
</p>
<br />

#### stretchShrink
<p>
  The stretchShrink property is the opposite of squishGrowth.  As the screen gets larger the element shrinks.  If applied to the width the height of the element will get shorter as the width of the screen gets larger.  If applied to the height the width of your element will shrink as the screen gets taller.  Instead of having a max property the stretchShink uses a <b><i>min</i></b> property to prevent the element from shrinking out of view.  The <b><i>start</i></b> property is the point at which the shrinking should begin to occur as the screen becomes larger.  The <b><i>speed</i></b> setting works the same so there’s no need to reiterate.  
</p>

<p>
  Each of these properties are categorized as one of three behavior types which goes as follows.
</p>
<br /><br />

#### Stationary
<p>
  The <b><i>baseSize</i></b> and <b><i>chaseStop</i></b> properties are considered stationary because the element stays at the defined size only adapting according to the speed setting of the size used.
</p>
<br />

#### Reactive
<p>
  The <b><i>crushGap</i></b> and <b><i>edgeChase</i></b> properties are considered reactive because the element breaks out of a stationary state to adjust with the size of the screen.
</p>
<br />

#### Counter Reactive
<p>
  The <b><i>squishGrowth</i></b> and <b><i>stretchShrink</i></b> properties are considered counter reactive because they react against the scaling of the screen by either expanding as the screen shrinks or shrinking as the screen expands.
</p>
<br /><br /><br />

# How To Use The srcryBox Class
<p>
  Now that you understand the purpose of each property lets look at some examples of how to use them in your code.  First add the <b><i>srcryBox</i></b> class to your HTML element along with your own class name as follows
</p>
<br />

```html
<div class="srcryBox myClass">
  ...
</div>
```

<br />
<p>
  If you want your element to have a base width of <b><i>hiMed-1-6</i></b> and a base height of <b><i>xTiny-2-3</i></b> you would do the following.
</p>
<br />

```css
.myClass{
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
}
```

<br />
<p>
  Now lets say you want the height of your element just a little bit taller but <b><i>hiMed-1-1</i></b> is bigger than you want and <b><i>xTiny-2-4</i></b> scales up faster than you prefer.  This is where the nudge property can be useful so you may want to do something like below.
</p>
<br />

```css
.myClass{
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
  --baseSize-h-nudge-slice : 5;
}
```

<br />

<p>
  If you look back at the table in the <b><i>boxSize</b></i> section you'll see the core pixel size of <b><i>hiMed-1-1</i></b> is 521px.  Most mobile screens are smaller than that in portrait view which means it will be too wide, this is where the <b><i>crushGap</i></b> property can be used.  Lets say you only want a margin of roughly 10px on each side of your element assuming its' centered on the page.  <b><i>xTiny-1-1</i></b> has a core size of 18px which would leave you with a 9px margin on each side of your element.  You would define it as demonstrated below.  
</p>
<br />

```css
.myClass{
  --crushGap-w : var(--xTiny-1-1);
    
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
  --baseSize-h-nudge-slice : 5;
  }
```

<br />
<p>
  Now lets say when looking at your layout on a screen 800px wide and above your element starts to look a little smaller in proportion than you prefer.  Lets say you don’t want any more than a 100px margin on each side of your element on each side.  Looking at the chart we can see that <b><i>small-2-1</i></b> has a core pixel value of 199px so we could use that size for the <b><i>edgeChase</i></b> to maintain that amount of space.  Lets also say you don’t want your element to grow any larger than roughly 1300px, <b><i>large-2-1</i></b> has a core size of 1364px so you could use that for the <b><i>chaseStop</i></b> property.  Because we want our sizes to be flexible and stay in portion with the screen we can use a higher speed setting than 1 so lets go with 6.
</p>
<br />

```css
.myClass{
  --crushGap-w : var(--xTiny-1-1);
    
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
  --baseSize-h-nudge-slice : 5;
  
  --edgeChase-w : var(--small-2-6);
  --chaseStop-w : var(--large-2-6);
  }
```

<br />
<p>
  Now let's say if the screen size is smaller than 500px you want the element to get a little taller so the user can interact with it better using their fingers.  Let’s also say you don’t want it to get any bigger than roughly 80px which is in range of <b><i>tiny-2-1</i></b> and you want it to reach the maximum height fairly fast.  This is where we can make use of the <b><i>squishGrowth</i></b> property.
</p>
<br />

```css
.myClass{
  --crushGap-w : var(--xTiny-1-1);
  
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
  --baseSize-h-nudge-slice : 5;

  --edgeChase-w : var(--small-2-6);
  --chaseStop-w : var(--large-2-6);

  --squishGrowth-h-start : 500px;
  --squishGrowth-h-max   : var(--tiny-2-1);
  --squishGrowth-h-speed : 16;
}
```

<br />
<p>
  Let’s say once the screen reaches 1100px you want the height of it to get shorter as it will most likely be on a computer where the user is interacting through a mouse rather than a finger tip and around 20px or so is ideal.  This is where we can make use of the <b><i>stretchShrink</i></b> property.
</p>
<br />

```css
.myClass{
  --crushGap-w : var(--xTiny-1-1);
  
  --baseSize-w : var(--hiMed-1-6);
  --baseSize-h : var(--xTiny-2-3);
  --baseSize-h-nudge-slice : 5;

  --edgeChase-w : var(--small-2-6);
  --chaseStop-w : var(--large-2-6);

  --squishGrowth-h-start : 500px;
  --squishGrowth-h-max   : var(--tiny-2-1);
  --squishGrowth-h-speed : 16;
  
  --stretchShrink-h-start : 1100px;
  --stretchShrink-h-min   : var(--xTiny-1-3);
  --stretchShrink-h-speed : 1;
}
```

<br />
<p>
  The srcryBox class has one more property called <b><i>bleed</i></b> which is borrowed from the printing industry.  The bleed on a printed document is pretty much a margin around the entire document where all the printable content should be contained.  So if you have an element nested inside of an element that you want to have a consistent margin you could do the following.
</p>
<br />

```css
.parentElement{
  display     : grid;
  place-items : center;
  width  : 600px;
  height : 600px;
}
  
.childElement{
  display : block;
  --baseSize-w  : 100%;
  --baseSize-h  : 100%;
  --bleed-scale : var(--micro-2-5);
}
```

<br />
<p>
  Below is a list of all available properties in the srcryBox class.
</p>
<br />

```
  --crushGap-w
  --crushGap-w-nudge-slice
  --crushGap-w-nudge-chunk
  --crushGap-h
  --crushGap-h-nudge-slice
  --crushGap-h-nudge-chunk
  
  --baseSize-w
  --baseSize-w-nudge-slice
  --baseSize-w-nudge-chunk
  --baseSize-h
  --baseSize-h-nudge-slice
  --baseSize-h-nudge-chunk
  
  --edgeChase-w
  --edgeChase-w-nudge-slice
  --edgeChase-w-nudge-chunk
  --edgeChase-h
  --edgeChase-h-nudge-slice
  --edgeChase-h-nudge-chunk
  
  --chaseStop-w
  --chaseStop-w-nudge-slice
  --chaseStop-w-nudge-chunk
  --chaseStop-h
  --chaseStop-h-nudge-slice
  --chaseStop-h-nudge-chunk
  
  --squishGrowth-w-start
  --squishGrowth-w-speed
  --squishGrowth-w-max
  --squishGrowth-w-max-nudge-slice
  --squishGrowth-w-max-nudge-chunk
  --squishGrowth-h-start
  --squishGrowth-h-speed
  --squishGrowth-h-max
  --squishGrowth-h-max-nudge-slice
  --squishGrowth-h-max-nudge-chunk
  
  --stretchShrink-w-start
  --stretchShrink-w-speed
  --stretchShrink-w-min
  --stretchShrink-w-min-nudge-slice
  --stretchShrink-w-min-nudge-chunk
  --stretchShrink-h-start
  --stretchShrink-h-speed
  --stretchShrink-h-min
  --stretchShrink-h-min-nudge-slice
  --stretchShrink-h-min-nudge-chunk
  
  --bleed-scale  
```

<br /><br /><br />

## srcryTxt Class

<p>
  The srcryTxt class helps you easily format your paragraph text using a few custom properties.  These properties are <b><i>text-size</i></b>, <b><i>text-nudge-amt</i></b>, <b><i>kerning-nudge-amt</i></b> and <b><i>leading-nudge-amt</i></b>.  The purpose these properties serve goes as follows.
</p>
<br />

#### text-size

<p>
  For setting the size of your text
</p>

#### text-nudge-amt

<p>
  For adjusting the size of your text in tiny increments to fine tune the perfect size.
</p>

#### kerning-nudge-amt

<p>
  For adjusting the spacing between the letters in your text.
</p>

#### leading-nudge-amt

<p>
  For adjusting the line height of your text.
</p>
<br />

<p>
  Even without setting the kerning or leading the srcryTxt class has default settings that do this automatically simply by applying the class to your paragraph elements.  The way you go about using them goes as follows.
</p>
<br />

```html
<p class="srcryTxt myClass">
  ...
</p>
```

<br />

```css
.myClass{
  --text-size : var(--text-article-4);
  --text-nudge-amt    : 3;
  --kerning-nudge-amt : 6;
  --leading-nudge-amt : 11;
}
```

<br /><br /><br />

# Conclusion
<p>
  Using srcry in your projects will give you finer control over your elements and how they scale.  This allows you to save your media queries exclusively for drastic layout changes rather than taming your text and elements every few pixels.  If you would like to become a contributor to this project feel free to join and share your code snippets to help other developers achieve awesome designs using this tool.
</p>
