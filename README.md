
# ``<CARD-T>`` - 52 playingcardts in **one** Custom Element ♥️

**This project uses modern browser technologies, use the latest Chrome or Firefox**

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

## The **single file** [element.card-t.js](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) is:

* W3C Custom Element: ``<card-t> </card-t>``

* SVG data for 52 playing cards - **500 KB** painstakingly slimmed to **148 KB**

* Total **gzip** file size: **63 KB creating 52 playingcardts:**


![](https://i.imgur.com/sVahVJO.jpg)

<hr>

# Why another SVG playing card

A 'Hello World!' App with Framework **X** used  **95 KiloBytes** ... to display 12 characters.

Something did not feel right!

I learned to [PEEK and POKE](https://en.wikipedia.org/wiki/PEEK_and_POKE) at the age of 10 on a [TRS-80](https://en.wikipedia.org/wiki/TRS-80) and learned HTML (a bit late) at **25**  
The ability to 'peek at' and learn from someone else's effort was fantastic.  
In the past years 'Web Development' has become *For-Rocket-Scientists-Only*  

**What happened to the days when all you needed were some HTML tags and a text-editor?**

[W3C standard Custom Elements](https://www.dannymoerkerke.com/blog/web-components-will-replace-your-frontend-framework)¹ make writing semantic HTML as cool as it was in my early days .. **without any Framework!**  

Playingcard(t)s are a good subject to demonstrate the power of a Custom Element

* one single file creates a ``<card-t>`` element
* attributes for configuration
* **no** external SVG images

Feel free to PEEK around, and if you want to POKE submit an [issue](https://github.com/card-ts/playingcardts/issues/new).

-- Danny Engelman  
-- Amsterdam 🌷🌷🌷 the Netherlands  
-- Summer 2019  👴🏽  _25 years after my first HTML page_

````
¹ - Everyone uses the terms Custom Elements & Web Components interchangeably.  
    Strictly speaking Web Components are Custom Elements WITH shadow DOM
````

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

# How the ``<card-t>`` Custom-Element works

For an introduction to W3C standard Custom Elements/WebComponents [read the excellent Blog by Danny Moerkerke](https://www.dannymoerkerke.com/blog/web-components-will-replace-your-frontend-framework)

Like the HTML5 ``<video>`` tag, the Custom Element ``<card-t>`` abstracts complex functionality into one HTML tag

💡 Custom Elements must be declared in a [Namespace](https://www.webcomponents.org/community/articles/how-should-i-name-my-element), so require a - hyphen in the tag name 

## Minimal HTML file to display a Queen of Hearts:

```html
  <html>
    <head>
        <script src='element.card-t.js'></script>
    </head>
    <body>
        <card-t rank=Queen suit=Hearts></card-t>
    </body>
  </html>
```

![](https://i.imgur.com/mfhk2pd.jpg)

**Custom Element ``<card-t>`` creates an image with the SVG as ``data:image`` src**

Saves you from headaches with SVG in a document (duplicate symbol ids, bleeding CSS etc.)  
and makes it easy to add HTML Drag-Drop functionality.

### How it looks in F12 Developer Tools:

![](https://i.imgur.com/7csZylT.jpg)

💡 Drag a card image to your desktop to see the created SVG 

Since ``<card-t>`` only creates a single IMG **no shadow-DOM is used**, thus IMG can be styled with **global CSS**.

```css
    [rank="queen"] img {
       border: 3px solid greenyellow;
       transform: rotate(15deg);
    }
```

![](https://i.imgur.com/Qdgf30L.jpg)

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

# My next challenge a Solitaire game in Custom Elements

```html
  <cardts-game>
    <cardts-deck type="frenchdeck"></cardts-deck>
    <cardts-pile>
      <% 7 times %>
        <cardts-pile type="sequence"></cardts-pile>
      <%%>
    </cardts-pile>
    <cardts-pile id="foundation" type="stack">
      <% 4 times %>
        <cardts-pile></cardts-pile>
      <%%>
    </cardts-pile>
  <cardts-game>
```

## or even weirder ``<card-t>`` games ...

What if cardts could:

* change suit during a game
* fade out during a game
* change from Queens to Kings
* ...
* ...

![](https://i.imgur.com/y3wKtcE.jpg)

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

![](https://i.imgur.com/gqOUijq.jpg)

# ``<card-t>`` attribute syntax

**playingcardts Terminology:**

* 'court' is UK English for 'face' US English. So Jack, Queen and King are **court**-cards (courts)
* SHDC is short for Spades-Hearts-Diamonds-Clubs 
* 0123 are Array indexes 

**``<card-t>`` takes a sh*tload of attributes you can play with:**

* ``letters`` - Custom localized suit letters 
* ``courts`` - mix court images
* ``suits`` - Mix suit/court images
* ``suitcolor`` - Change SHDC suit color
* ``cardcolor`` - card color
* ``opacity`` - set card content opacity
* ``courtcolors`` - Change court image colors
* ``bordercolor`` - set card border color
* ``borderradius`` - set card border radius
* ``borderline`` - set card border line thickness

# 🔧 ``letters`` - Custom localized suit letters 

default: AJQK 

Rename Ace, Jack, Queen, King letters AJQK to Dutch locale 'Aas Boer Vrouw Heer'

````HTML
    <card-t suit=Spades   rank=Ace   letters=ABVH></card-t>
    <card-t suit=Hearts   rank=Jack  letters=ABVH></card-t>
    <card-t suit=Diamonds rank=Queen letters=ABVH></card-t>
    <card-t suit=Clubs    rank=King  letters=ABVH></card-t>
````

![](https://i.imgur.com/y83wjG8.jpg)

notes: 

  * a 4 letter string is used so it can be a global setting for all created cards

  * Custom ``letters`` draw **all** ranks (A,2,3, etc.) in Arial font

  * ``letters`` can not be Emoji (Unicode strings)

# 🔧 ``courts`` - mix court images

default: 012

Rearrange SHDC court images to KJQ:

````html
    <card-t suit=Hearts   rank=Jack  courts=201></card-t>
    <card-t suit=Spades   rank=Queen courts=201></card-t>
    <card-t suit=Diamonds rank=King  courts=201></card-t>
````

![](https://i.imgur.com/sw8hWDi.jpg)

# 🔧 ``suits`` - Mix suit/court images

default: 0123

Change Spades=0, Hearts=1, Diamonds=2, Clubs=3 court image:

````HTML
    <card-t suit=S rank=Queen suits=0000></card-t>
    <card-t suit=H rank=Queen suits=0000></card-t>
    <card-t suit=D rank=Queen suits=0000></card-t>
    <card-t suit=C rank=Queen suits=0000></card-t>
````

Uses Spades court images for all 4 suits

Yes, that 148 KB of SVG data could be reduced to 25%  (not in this version!)

Who will notice all cards use the same court image?

![](https://i.imgur.com/D9qFMP5.jpg)

💡 The Diamond court image (suits=2222) is not suitable for Spades, Hearts and Clubs cards because the top-half of cards are rotated 180 degrees to create the bottom-half, and only the Diamond makes a valid image (see card center) when rotated 180 degrees

![](https://i.imgur.com/t3jR5bz.jpg)

# 🔧 ``backcolor`` - card backside color

default: #E55 (red)

````html
    <card-t rank=0 backcolor="red"  ></card-t>
    <card-t rank=0 backcolor="green"></card-t>
    <card-t rank=0 backcolor="#44F" backtext="COPYRIGHT" backtextcolor=black></card-t>
````

![](https://i.imgur.com/GxT3m91.jpg)

# 🔧 ``suitcolor`` - Change SHDC suit color

default: #000,red,red,#000

# 🔧 ``cardcolor`` - card color

default: #FFF

````html
    <card-t rank=1 suit=0 suitcolor="#FFF,#FFF,#FFF,red"   cardcolor="red"       ></card-t>
    <card-t rank=1 suit=1 suitcolor="#FFF,yellow,#FFF,red" cardcolor="green"     ></card-t>
    <card-t rank=1 suit=2 suitcolor="#FFF,#FFF,black,red"  cardcolor="dodgerblue"></card-t>
    <card-t rank=1 suit=3 suitcolor="#FFF,#FFF,#FFF,red"   cardcolor="yellow"    ></card-t>
````

💡 You need to specify all 4 colors even when only applying one suit

Since the string is converted to an array the above can be written as:

````html
    <card-t rank=1 suit=0 suitcolor="#FFF,"    cardcolor="red"       ></card-t>
    <card-t rank=1 suit=1 suitcolor=",yellow," cardcolor="green"     ></card-t>
    <card-t rank=1 suit=2 suitcolor=",,black," cardcolor="dodgerblue"></card-t>
    <card-t rank=1 suit=3 suitcolor=",,,red"   cardcolor="yellow"    ></card-t>
````

💡 non-color values will break the SVG suit display... So.. if you want a card without suits.. force an error :-)

💡 add attribute ``norank=true`` and only the big center suit remains

![](https://i.imgur.com/uvGJKQX.jpg)

# 🔧 ``opacity`` - set card content opacity

default: 0.8 

💡 0.8 makes the cards look not too sharp, and you can highlight card-ts by setting opacity to 1

````html
    <card-t rank=1 suit=0 opacity=1  ></card-t>
    <card-t rank=1 suit=1 opacity=.75></card-t>
    <card-t rank=1 suit=2 opacity=.5 ></card-t>
    <card-t rank=1 suit=3 opacity=.1 ></card-t>
````

💡 CSS opacity makes the whole IMG transparent, ``<card-t opacity=.5>`` leaves the card **backcolor** at 100%

![](https://i.imgur.com/eZhAuob.jpg)

# 🔧 ``bordercolor`` - set card border color

default: black

# 🔧 ``borderradius`` - set card border radius

default: 12

# 🔧 ``borderline`` - set card border line thickness

default: 1.5

````html
    <card-t rank=1  suit=0 bordercolor=red     borderradius=12   borderline=12></card-t>
    <card-t rank=4  suit=0 bordercolor=hotpink borderradius=100% borderline=20></card-t>
    <card-t rank=13 suit=H bordercolor=gold    borderradius=12   borderline=38></card-t>
````

![](https://i.imgur.com/pdbp75j.jpg)

# ☠️ ``courtcolors`` - Change court image colors

**this setting will most likely be gone in 'less SVG' version 2**

default: #DB3,red,#44F,#000,#000,4  (gold,red,blue,black,blacklines,linethickness)

````html
    <card-t suit=Hearts   rank=Jack  courtcolors=gold,red,blue,black,black,4               ></card-t>
    <card-t suit=Spades   rank=Queen courtcolors=#DB3,lightcoral,lightblue,slategray,#000,1></card-t>
    <card-t suit=Diamonds rank=King  courtcolors=gold,red,green,orange,#000,4              ></card-t>
````

💡 suit decorations are set by the ``suitcolor`` attribute

![](https://i.imgur.com/D2hwgrC.jpg)

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

# How I reduced 500 KB SVG to 148 KB

All good open-source SVG playingcards available are high-precision ready for print. 

* I started with the 550 KB for 52 CC-0 licensed cards from the [card generator by Adrian Kennard](https://www.me.uk/cards/)
* reduced precision with: [Jake Archibalds GUI for SVGO](https://jakearchibald.github.io/svgomg/)
* manually reduced details in the cards you don't see on a computer screen
* cut everything up in separate SVG paths
* made redundant paths into single JS functions
* the SVG data is now 148 KB , this can be made smaller with some more elbow grease using [Inkscape](https://inkscape.org/).
* wrote a ``SVGcardt()`` function to create an IMG with SVG data
* and cleaned up some courts which (since ages) had the suit on the wrong? side

![](https://i.imgur.com/9euOd0r.jpg)

### A note on data compression

Using a [LZMA compressor](http://lzma-js.github.io/LZMA-JS/demos/advanced_demo.html) that **148** KB can be reduced to **55 KB**  
You then need to transport it over HTTP as Base64 making it 67 KB  
And the Browser needs to decompress the data which takes a hefty 200ms

Version 1 did de-compression and lazy loaded all 12 court images.

Since gzip is a similar compression (over the whole file)  
there is only a gain on really-really slow 3G connections (download takes 5 instead of 6 seconds)

<hr>

# Frequently Asked Questions

### 🃏 Why ``<card-t>``

A Custom Element requires its own [Namespace](https://www.webcomponents.org/community/articles/how-should-i-name-my-element), so you are stuck to something with a - hyphen.

You can create 52 Custom Elements (extended from ``<card-t>``):

````html
  <queen-of-hearts></queen-of-hearts>
  <ten-of-spades></ten-of-spades>
  ...
````

But there is little value as you can not use **partial** Selectors for tag names.  
To select all Spades you still need attributes:

````html
  <queen-of-hearts hearts></queen-of-hearts>
  <ten-of-spades spades></ten-of-spades>
  ...
````

### 🃏 How about separating Element and SVG data?

Yes, an option is to exclude the (compressed/raw) SVG data from the Element file.  
The Element can then fetch the data asynchronous.

This project was about stuffing everything into **one** file.

### 🃏 Where is the NPM installer?  

If you need an installer to copy **one** file: [element.card-t.js](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js)  
You might find a better career flipping burgers at McDonalds.

### 🃏 Where is the ``SVGcardt()`` source?

The ``<card-t>`` Custom Element declaration in [element.card-t.js](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) is Open Source.  
You can rename ``<card-t>`` to anything you want and customize the Custom Element to your liking.

The SVG creation code took some blood, sweat and tears and is closed source for now. 

**You do NOT need the ``SVGcardt()`` _Source Code_ to use ``<card-t>`` in applications**

### 🃏 Are cardts really created in the browser/not downloaded?

See F12 Network tab, ``data:image/svg`` cardts take **0 milliseconds** download time 

![](https://i.imgur.com/ieN7gvc.jpg)

### 🃏 Where is the Joker?

🤣 Probably causing havoc in Gotham City?

I haven't found a good Joker Card design yet, if you have one let me know

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

# Challenge - built a game using ``<card-t>``

Create FreeCell with HTML Custom Elements

inspiration: https://www.free-freecell-solitaire.com/freecell.html

**(something like) This HTML should create ALL game functionality**

```html
  <cardts-game>
    <cardts-pile id="freecells" type="any">
      <% 4 times %>
        <cardts-pile max=1></cardts-pile>
      <%%>
    </cardts-pile>
    <cardts-pile id="foundation" type="stack">
      <% 4 times %>
        <cardts-pile></cardts-pile>
      <%%>
    </cardts-pile>
    <cardts-pile>
      <% 8 times %>
        <cardts-pile type="sequence"></cardts-pile>
      <%%>
    </cardts-pile>
    <cardts-deck type="frenchdeck"></cardts-deck>
  <cardts-game>
```

## Here is some help to create the foundation for the foundation piles:

````html
    <card-t foundation=Spades></card-t>
    <card-t foundation=Hearts></card-t>
    <card-t foundation=2></card-t>
    <card-t foundation=C></card-t>
````

![](https://i.imgur.com/F5v8Ud7.jpg)

<hr>

[https://card-ts.github.io/playingcardts/](https://card-ts.github.io/playingcardts/) - 📄 [source](https://github.com/card-ts/playingcardts/blob/master/element.card-t.js) - 🤸 Play on: [JSFiddle](https://jsfiddle.net/dannye/Lvbqtj9d/) , [CodePen](https://codepen.io/Danny-Engelman/project/editor/ZRoWyM)

<hr>

# (some) Used Resources

## Custom Elements/Web Components

* Custom Elements/Web Components best practices  
https://developers.google.com/web/fundamentals/web-components/best-practices

#### Cards

* [The International Playing-Card Society](https://www.i-p-c-s.org/)

* Comparison of multiple solutions: https://socialcompare.com/en/comparison/css-playing-cards-pgnq7dx

* SVG (server side) Card Creator (I used these and altered them)  
https://www.me.uk/cards/makeadeck.cgi
* ES6/Polymer WebComponent - separate SVG files for courts (last commit:2017)  
https://www.webcomponents.org/element/vpusher/game-card
* CSS playing cards - PNG images (over 250 Kb) (last commit: 2012)  
https://donpark.github.io/scalable-css-playing-cards/
* HTML5 deck of cards (all 52 cards are separate SVG files) (last commit: 2017)  
https://github.com/pakastin/deck-of-cards  
https://deck-of-cards.js.org/
* CSS only (no Court images) (last commit: 2012)  
https://github.com/zachwaugh/Helveticards
* PNG card background image = https://bfa.github.io/solitaire-js/img/card_back_bg.png
* [Google Images playingcards](https://www.google.com/search?q=old+52+cards&tbm=isch&tbs=rimg:CQvmkLdr_14McIjgYvxv84K-eaVXk-0nLcJFF3OanFgQriEXAiZjXEp9zM2hJ2fYh1rUdAmXW8kROLnUlky-kQYhn7SoSCRi_1G_1zgr55pEZomC09EhU8oKhIJVeT7SctwkUURF50UBpuCFl0qEgnc5qcWBCuIRRGBNOuJrmaMECoSCcCJmNcSn3MzESHqEP4mrUbzKhIJaEnZ9iHWtR0R9s1Zi32qMiwqEgkCZdbyRE4udRFP-xbZjpVQIioSCSWTL6RBiGftEX2c9kdcxbzu&tbo=u&sa=X&ved=2ahUKEwjCgrW0x6nhAhXCDOwKHbHpDiIQ9C96BAgBEBs&biw=1920&bih=947&dpr=1#imgrc=GL8b_OCvnml8hM:)

* Solitaire
    * Redux,React, the lot https://codepen.io/HunorMarton/details/rwpGXj

    * (2017) No frameworks/library No drag drop, PNG images for courts
    https://bfa.github.io/solitaire-js/  
    https://github.com/bfa/solitaire-js

#### SVG
* SVGO GUI - https://jakearchibald.github.io/svgomg/
* http://www.petercollingridge.appspot.com/svg-editor

#### LZMA compression
* http://lzma-js.github.io/LZMA-JS/demos/advanced_demo.html
* https://github.com/LZMA-JS/LZMA-JS
* https://dafrok.github.io/gzip-size-online/
* Analyze GZ compression:  
https://encode.ru/threads/1889-gzthermal-pseudo-thermal-view-of-Gzip-Deflate-compression-efficiency

<hr>
<hr>
