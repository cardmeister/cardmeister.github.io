## 52 SVG playingcards in **one** 16 KB² Custom Element: `<CARD-T>`

#### No Frameworks&nbsp;&nbsp; No Dependencies&nbsp;&nbsp; No External SVG files!&nbsp;&nbsp; All SVG is created by the Custom Element

##### From the maker of: [FlagMeister.github.io](https://flagmeister.github.io) , [ChessMeister.github.io](https://chessmeister.github.io)

![](https://i.imgur.com/SeQwXST.jpg)

> This project uses modern browser technologies. Open in a 'evergreen' browser  
> If you want to make it work in outdated browsers see the [WebComponents polyfill](https://www.webcomponents.org/polyfills/)

**License:** Unlicense: This is free software released into the public domain - https://choosealicense.com/licenses/unlicense/

<hr>

## The **single file** [elements.cardmeister.min.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.min.js) is:

- SVG data for 52 playing cards - **500 KB** painstakingly slimmed

- one [W3C Autonomous Custom Element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) : `<card-t cid=Queen-of-Hearts> </card-t>`

- 52 customized Built-In IMG elements : `<img is=queen-of-hearts>` 

- Total **GZip** file size: (under) **16 KB² creating 52 playingcards:**

![](https://i.imgur.com/Wy7jqLR.jpg)

<hr>

# Why another SVG playing card

A 'Hello World!' with Framework **X** took hours installing tools and used **95 KiloBytes** ... to display 12 characters.

**Something did not feel right!**  
**What happened to the days when all you needed were some HTML tags and a text-editor?**

I learned to [PEEK and POKE](https://en.wikipedia.org/wiki/PEEK_and_POKE) at the age of 10 on a [TRS-80](https://en.wikipedia.org/wiki/TRS-80) and learned HTML (a bit late) at **25**  
The ability to 'peek at' and learn from someone else's effort was fantastic.

Alas in the past years 'Web Development' has become something _For-Rocket-Scientists_ only

[W3C standard Custom Elements](https://www.dannymoerkerke.com/blog/web-components-will-replace-your-frontend-framework)¹ make writing semantic HTML as cool as it was in my early days .. **without any Framework!**

Playingcard(t)s are a good subject to demonstrate the power of a Custom Element

- one single file creates a `<card-t>` Custom Element
- (loads of) attributes for configuration
- 52 SVG playingcards
- **no** external SVG images
- All in 16 KB² because my first computer had 16 **Kilo**Bytes memory

Feel free to PEEK around, and if you want to POKE, submit an [issue](https://github.com/cardmeister/cardmeister.github.io/issues/new).

A special thanks to users _Supersharp_ and _Intervalia_ for their always helpful answers on [StackOverflow](https://stackoverflow.com/questions/tagged/web-component+or+custom-element)!

-- Danny Engelman  
-- Amsterdam 🌷🌷🌷 the Netherlands  
-- Summer 2019 👴🏽 _25 years after my first HTML page_

1. The terms _Custom Elements_ & _Web Components_ are used interchangeably.  
   [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) is the umbrella term for the three main techonologies:

   - [Custom Elements - the Custom Elements **API**](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements)
   - [Shadow Dom](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) (not used in this project)
   - [HTML Templates](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots) (not used in this project)
   - some references include a fourth: [ES Modules](https://developer.mozilla.org/en-US/docs/Mozilla/JavaScript_code_modules) (not used in this project)

2. Minified 16 KB GZip  
   It is a card game .. I cheated ... but can you spot where? (explained in documentation below)

<hr>

# How the `<card-t>` Custom-Element works

For an introduction to W3C standard Custom Elements/WebComponents [read the excellent Blog by Danny Moerkerke](https://www.dannymoerkerke.com/blog/web-components-will-replace-your-frontend-framework)

Like the HTML5 `<video>` tag, the Custom Element `<card-t>` abstracts complex functionality into one HTML tag

💡 Custom Elements must be declared in a [Namespace](https://www.webcomponents.org/community/articles/how-should-i-name-my-element), so require a - hyphen in the tag name

## Minimal HTML file to display a Queen of Hearts:

```html
<html>
  <head>
    <script src="elements.cardmeister.full.js"></script>
  </head>
  <body>
    <card-t rank="Queen" suit="Hearts"></card-t>
  </body>
</html>
```

![](https://i.imgur.com/mfhk2pd.jpg)

**(Autonomous) Custom Element `<card-t>` creates an image with the SVG as `data:image` src**

Saves you from headaches with SVG in a document (duplicate symbol ids, bleeding CSS etc.)  
and makes it easy to add HTML Drag-Drop functionality.

💡 Autonomous Custom Elements require a closing tag: `</card-t>`

#### How it looks in F12 Developer Tools:

![](https://i.imgur.com/7csZylT.jpg)

## Customized Built-In Element (from IMG)

52 Custom Elements are **also** created customizing the IMG element so you can use:

```html
<img is="ten-of-hearts" />
<img is="jack-of-hearts" />
<img is="queen-of-hearts" />
<img is="king-of-hearts" />
<img is="ace-of-hearts" />
```

> The _Autonomous_ Custom Element `<card-t>` and the _Customized Built-In_ Element `<img is=...>`  
> are two different flavours of Custom Elements which (in this case) do the same.  
> You can pick the **one** that suits your application. Or use them both in one page: [https://cardmeister.github.io](https://cardmeister.github.io)

💡 requires a <a href="https://www.webcomponents.org/polyfills">polyfill</a> in Safari, because Apple does not want to implement this part of the spec.

💡 declaration **must be** all lowercase!

💡 the IMG element is self-closing by default, no closing tag required!

💡 the `is=` declaration only takes effect when the DOM element is created

💡 on the (customized IMG) element you can use all attributes/properties documented below

👨‍💻 tech: Autonomous Elements _can_ have [ShadowDom](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM), Customized Elements can **not** have [ShadowDom](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM)

👨‍💻 tech: Because IMG elements don't contain text or have descendants, neither CSS selector `img:before` or `img:after` can be used

![](https://i.imgur.com/MNoSbdo.jpg)

# Styling `<card-t>` with CSS:

Since `<card-t>` only creates a single IMG **no shadow-DOM is required/used**, thus IMG can be styled with **global CSS**:

```css
[rank="queen"] img {
  border: 3px solid greenyellow;
  transform: rotate(15deg);
}
```

or for the customized IMG element:

```css
img[is*="queen"] {
  border: 3px solid greenyellow;
  transform: rotate(15deg);
}
```

![](https://i.imgur.com/Qdgf30L.jpg)

<hr>

# My next challenge: a Solitaire game in Custom Elements

I have the selection and drag/drop part nearly done: https://card-ts.github.io/Solitaire/

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
  <cardts-game></cardts-game
></cardts-game>
```

## or even weirder `<card-t>` games ...

What if cardts could:

- change suit during a game
- fade out during a game
- change from Queens to Kings
- ...
- ...

![](https://i.imgur.com/y3wKtcE.jpg)

<hr>
<hr>
<hr>

![](https://i.imgur.com/gqOUijq.jpg)

# `<card-t>` attribute/properties syntax

**playingcards Terminology:**

- 'court' is UK English for 'face' US English. So Jack, Queen and King are **court**-cards (courts)
- SHDC is short for Spades-Hearts-Diamonds-Clubs
- 0123 are Array indexes (SHDC)
- cid = card id  
  As = Ace of Spades , TD = Ten of Diamonds

💡 attributes can be written as attributes in HTML:`<card-t id=MyCard cid=Qh ></card-t>`

💡 attributes can be set as attribute:`MyCard.setAttribute('cid','Kh')`

💡 or as property: `MyCard.cid='Kh'` (sets the attribute value)

### `<card-t>` takes a sh\*tload of attributes you can play with:

See: [https://cardmeister.github.io](https://cardmeister.github.io)

- `cid` - Standard Card ID notation: `cid=Qh` = Queen of Hearts
- `letters` - Custom localized court letters
- `courts` - mix rank/courts images
- `suits` - Mix suit/court images
- `suitcolor` - Change SHDC suit color
- `cardcolor` - card color
- `opacity` - set card content opacity
- `courtcolors` - Change court image colors
- `bordercolor` - set card border color
- `borderradius` - set card border radius
- `borderline` - set card border line thickness
- `backtext` - card backside text
- `backtextcolor` - card backside color
- `svg` - (undocumented) add attributes to main SVG definition (eg: svg="transform='rotate(5,5,5)'")
- `pips` - (undocumented) custom suitsymbols (pips) on number cards

# 🔧 `cid` - standard card id notation

```HTML
    <card-t cid=As></card-t>
    <card-t cid=5d></card-t>
    <card-t cid=Tc></card-t>
    <card-t cid=Jh></card-t>
    <card-t cid=Qc></card-t>
```

💡 overrules `rank=` and `suit=` notation

💡 case **in**sensitive: `qC` is the same as: `Qc`

💡 `10C` is processed as `TC`

💡 `Queen-of-Clubs` is processed as `Qc`

💡 `<img is=queen-of-clubs>` uses `cid` internally - **`is=` requires lowercase full Element name!!**

![](https://i.imgur.com/lI8sa0p.jpg)

# 🔧 `letters` - Custom localized court letters

default: AJQK

Rename Ace, Jack, Queen, King letters AJQK to Dutch locale 'Aas Boer Vrouw Heer'

```HTML
    <card-t suit=Spades   rank=Ace   letters=ABVH></card-t>
    <card-t suit=Hearts   rank=Jack  letters=ABVH></card-t>
    <card-t suit=Diamonds rank=Queen letters=ABVH></card-t>
    <card-t suit=Clubs    rank=King  letters=ABVH></card-t>
```

![](https://i.imgur.com/y83wjG8.jpg)

💡 a 4 letter string is used so it can be a global setting for all created cards

💡 Custom `letters` draw **all** ranks (A,2,3,4 etc.) in Arial font

💡 `letters` can **not** be Emoji (Unicode strings)

# 🔧 `courts` - mix rank/courts images

default: 012

Before anyone complains the Queen is always #2

Rearrange SHDC court images to KJQ = 201 :

```html
<card-t suit="Hearts" rank="Jack" courts="201"></card-t>
<card-t suit="Spades" rank="Queen" courts="201"></card-t>
<card-t suit="Diamonds" rank="King" courts="201"></card-t>
```

![](https://i.imgur.com/sw8hWDi.jpg)

# 🔧 `backcolor` - card backside color

default: #E55 (red)

```html
<card-t rank="0" backcolor="red"></card-t>
<card-t cid="00"></card-t>
<card-t
  rank="0"
  backcolor="#44F"
  backtext="COPYRIGHT"
  backtextcolor="black"
></card-t>
```

![](https://i.imgur.com/GxT3m91.jpg)

# 🔧 `suitcolor` - Change SHDC suit color

default: #000,red,red,#000

# 🔧 `cardcolor` - card color

default: #FFF

```html
<card-t
  rank="1"
  suit="0"
  suitcolor="#FFF,#FFF,#FFF,red"
  cardcolor="red"
></card-t>
<card-t
  rank="1"
  suit="1"
  suitcolor="#FFF,yellow,#FFF,red"
  cardcolor="green"
></card-t>
<card-t
  rank="1"
  suit="2"
  suitcolor="#FFF,#FFF,black,red"
  cardcolor="dodgerblue"
></card-t>
<card-t
  rank="1"
  suit="3"
  suitcolor="#FFF,#FFF,#FFF,red"
  cardcolor="yellow"
></card-t>
```

The string (all 4 settings in one string for global declaration!) is converted to an array so can be written as:

```html
<card-t rank="1" suit="0" suitcolor="#FFF," cardcolor="red"></card-t>
<card-t rank="1" suit="1" suitcolor=",yellow" cardcolor="green"></card-t>
<card-t rank="1" suit="2" suitcolor=",,black" cardcolor="dodgerblue"></card-t>
<card-t rank="1" suit="3" suitcolor=",,,red" cardcolor="yellow"></card-t>
```

💡 You can change one card with: `element.suitcolor='blue';`

💡 non-color values will break the SVG suit display

💡 add attribute `norank=true` and only the big center suit remains

![](https://i.imgur.com/kd0dOZ1.jpg)

# 🔧 `opacity` - set card content opacity

default: 0.8

💡 0.8 makes the cards look not too sharp, and you can highlight card-ts by setting opacity to 1

```html
<card-t rank="1" suit="0" opacity="1"></card-t>
<card-t rank="1" suit="1" opacity=".75"></card-t>
<card-t rank="1" suit="2" opacity=".5"></card-t>
<card-t rank="1" suit="3" opacity=".1"></card-t>
```

💡 CSS opacity makes the whole IMG transparent! `<card-t opacity=n>` leaves the `<card-t>` **backcolor** at 100%

![](https://i.imgur.com/eZhAuob.jpg)

# 🔧 `bordercolor` - set card border color

default: #444 (darkgray)

# 🔧 `borderradius` - set card border radius

default: 12

# 🔧 `borderline` - set card border line thickness

default: 1

```html
<card-t
  rank="1"
  suit="0"
  bordercolor="red"
  borderradius="12"
  borderline="12"
></card-t>
<card-t
  rank="4"
  suit="0"
  bordercolor="hotpink"
  borderradius="100%"
  borderline="20"
></card-t>
<card-t
  rank="13"
  suit="H"
  bordercolor="gold"
  borderradius="12"
  borderline="38"
></card-t>
```

![](https://i.imgur.com/pdbp75j.jpg)

# ☠️ `courtcolors` - Change court image colors

<b style=color:lightcoral>this setting will most likely be gone in 'less SVG' version 2</b>

default: #DB3,red,#44F,#000,#000,4 (gold,red,blue,black,blacklines,linethickness)

```html
<card-t
  suit="Hearts"
  rank="Jack"
  courtcolors="gold,red,blue,black,black,4"
></card-t>
<card-t
  suit="Spades"
  rank="Queen"
  courtcolors="#DB3,lightcoral,lightblue,slategray,#000,1"
></card-t>
<card-t
  suit="Diamonds"
  rank="King"
  courtcolors="gold,red,green,orange,#000,4"
></card-t>
```

💡 suit decorations are set by the `suitcolor` attribute

![](https://i.imgur.com/D2hwgrC.jpg)

<hr>

# SVG cards are huge. How I reduced 500 KB SVG

All good open-source SVG playingcards available are high-precision ready for print.

In the [HTML5 deck of cards](https://deck-of-cards.js.org/) the **single** [King of Hearts 1_13.svg](https://deck-of-cards.js.org/faces/1_13.svg) **card is 69 KB**

![](https://i.imgur.com/WEgysvp.jpg)

### `<card-t>` creates all 52 cards in **16 KB**

![](https://i.imgur.com/0K09KNh.jpg)

- I started with the 550 KB for 52 CC-0 licensed cards from the [card generator by Adrian Kennard](https://www.me.uk/cards/)
- reduced precision with: [Jake Archibalds GUI for SVGO](https://jakearchibald.github.io/svgomg/)  
  (this causes some alignment 'errors' you only see viewing a court card full screen)
- spent some time in [Inkscape](https://inkscape.org/) reducing details you don't see on a computer screen
- cut everything up in separate SVG paths
- made redundant paths into single JS functions/variables
- (see below) cleaned up the Jack of Spades court which (since ages?) had the suit on the wrong? side
- wrote a `SVGcardt()` function to create an IMG with SVG data
- Re-drawing the Heart pips on the Jack, I saw an opportunity to cheat and save 70% of SVG data (see FAQ)

![](https://i.imgur.com/9euOd0r.jpg)

### A note on data compression

The SVG can be reduced more using a [LZMA compressor](http://lzma-js.github.io/LZMA-JS/demos/advanced_demo.html)  
But HTTP requires Base64 encoding.  
And the Browser needs to decompress the data which takes a hefty 200ms (and a 6.9KB decoder)

The first PoC did LZMA de-compression and lazy loaded all 12 court images.

Since GZip is a similar LZ compression technique (over the whole file) there is only a gain on slow 3G connections

<hr>

# Frequently Asked Questions

### 🃏 Why `<card-t>`

A Custom Element requires its own [Namespace](https://www.webcomponents.org/community/articles/how-should-i-name-my-element), so you are stuck to something with a - hyphen.

You can create 52 Autonomous Custom Elements (extend from `<card-t>`):

```html
<queen-of-hearts></queen-of-hearts>
<ten-of-spades></ten-of-spades>
...
```

But there is little value as you can not use **partial** Selectors for tag names.

To select all Spades you still need attributes:

```html
<queen-of-hearts hearts></queen-of-hearts>
<ten-of-spades spades></ten-of-spades>
...
```

Because `queen-of-hearts` can either be a 'Autonomous Custom Element' OR a 'Customized Built-In Element'  
`<card-t>` creates 52 Customized IMG elements:

```html
<img is="ten-of-hearts" />
<img is="jack-of-hearts" />
<img is="queen-of-hearts" />
<img is="king-of-hearts" />
<img is="ace-of-hearts" />
```

💡 declaration **must be** all lowercase!

💡 the IMG element is self-closing by default, no closing tag required!

💡 the `is=` declaration only takes effect when the DOM element is created

💡 on the (customized IMG) element you can use all attributes/properties documented above

![](https://i.imgur.com/MNoSbdo.jpg)

### 🃏 How about separating Element and SVG data?

Yes, an option is to exclude the (compressed/raw) SVG data from the Element file.  
The Element can then fetch the data asynchronous.

This project was about stuffing everything into **one** file.

### 🃏 Where is the NPM installer?

If you need an installer to copy **one** file: [elements.cardmeister.min.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.min.js)

You might find a better career flipping burgers at McDonalds.

Read: I stuck the **UNlicense** on this code. You can do whatever you want with the code.  
I don't want to be responsible for maintaining a dependency for others

### 🃏 Where is the `SVGcardt()` source?

**You do NOT need the `SVGcardt()` _Source Code_ to use `<card-t>` or `<img is=..>` in applications**

The `<card-t>` Custom Element declaration in [elements.cardmeister.min.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.min.js) is unlicensed.  
You can rename `<card-t>` to anything you want and customize the Custom Element to your liking.

The `<img is=..>` declaration is part of the minified SVGcardt() code.

The SVG creation code took some blood, sweat and tears and is closed source for now.  
It needs some refactoring and documentation before this is public ready.  
Watch this GitHub repo and you will know when it becomes available.

### 🃏 Are cardts really created in the browser/not downloaded?

See F12 Network tab, `data:image/svg` cardts take **0 milliseconds** download time

![](https://i.imgur.com/ieN7gvc.jpg)

Note: FireFox is noticeably slower in drawing the cards.

Creating the card does take CPU time. Maybe a WebWorker can improve performance (but I can't stick JScode and a WebWorker in **one** single file)

## 🃏 Where is the Joker?

😉 Causing havoc in Gotham City?!

I haven't found a good Joker Card design yet, if you have one let me know

## 🃏 Why not [..*fill in WC Library/Framework name*..] ?

I wanted to learn how far I could go with vanilla JavaScript  
Then I wanted to proof you don't need libraries/frameworks

<hr>

# 🃏 Where/How did you cheat to get all SVG in 16KB element?

Look closely at the court cards....

**The 16 KB version uses the same (JQK Hearts) court image with slightly different colors to distract your eye.**

# 🔧 `suits` - Mix suit/court images

default: 0123 &nbsp; (**defaults to 1111 in the 16 KB version!**)

Change Spades=0, Hearts=1, Diamonds=2, Clubs=3 court image:

```HTML
    <card-t suit=S rank=Queen suits=1111></card-t>
    <card-t suit=H rank=Queen suits=1111></card-t>
    <card-t suit=D rank=Queen suits=1111></card-t>
    <card-t suit=C rank=Queen suits=1111></card-t>
```

## Cheating Queens:

![](https://i.imgur.com/k6cmH4M.jpg)

## The full `<card-t>` version with 12 **unique** SVG courts:

![](https://i.imgur.com/sVkxGey.jpg)

The Full Version **[elements.cardmeister.full.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.full.js)** with 12 different court images adds **110 KB** raw SVG data

**Making the single file 60 KB GZipped!**

## See: [index.html?#full](https://cardmeister.github.io/index.html?#full&cid=Qh) - 📄 [source](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.full.js)

## Difference between the .min. and the .full. version

Apart from the court images there are no differences.

It was fun (and took some time) breaking that 16 KB barrier, and helped making the full version smaller as well.

**Use the Full version** !

- **[elements.cardmeister.full.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.full.js)**

The Min version can be used for slow/low-bandwidth applications.

- [elements.cardmeister.min.js](https://github.com/cardmeister/cardmeister.github.io/blob/master/elements.cardmeister.min.js)

<hr>

# Challenge - built a game using `<card-t>`

Create FreeCell with HTML Custom Elements

inspiration: https://www.free-freecell-solitaire.com/freecell.html

**(something like) This HTML should create ALL game functionality**

```html
<cardts-game>
  <cardts-pile id="freecells" type="any">
    <% 4 times %>
    <cardts-pile max="1"></cardts-pile>
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
  <cardts-game></cardts-game
></cardts-game>
```

## Here is some help to create the foundation for the SHDC foundation piles:

```html
<card-t cid="F0"></card-t>
<card-t cid="FH"></card-t>
<card-t cid="F2"></card-t>
<card-t cid="FC"></card-t>
```

![](https://i.imgur.com/F5v8Ud7.jpg)

<hr>

# License: unlicense

```
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
```

For more information, please refer to <http://unlicense.org>

<hr>

# You've got to know when to fold them...

https://www.youtube.com/watch?v=7hx4gdlfamo&t=1s

or the Muppets version: https://www.youtube.com/watch?v=kNnrTNFWcsg

![](https://i.imgur.com/m3VdphY.jpg)

<hr>

# (some) Used Resources

## Custom Elements/Web Components

- https://www.dannymoerkerke.com/blog/web-components-will-replace-your-frontend-framework
- https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements
- Custom Elements/Web Components best practices  
  https://developers.google.com/web/fundamentals/web-components/best-practices
- Andrea Giammarchi/WebReflection - Why I use WebComponents  
  https://gist.github.com/WebReflection/71aed0c811e2e88e3cd3c647213f0e6c

#### Cards

- [The International Playing-Card Society](https://www.i-p-c-s.org/)

- Comparison of multiple solutions: https://socialcompare.com/en/comparison/css-playing-cards-pgnq7dx

- SVG (server side) Card Creator (I used these and altered them)  
  https://www.me.uk/cards/makeadeck.cgi
- ES6/Polymer WebComponent - separate SVG files for courts (last commit:2017)  
  https://www.webcomponents.org/element/vpusher/game-card
- CSS playing cards - PNG images (over 250 Kb) (last commit: 2012)  
  https://donpark.github.io/scalable-css-playing-cards/
- HTML5 deck of cards (all 52 cards are separate SVG files) (last commit: 2017)  
  https://github.com/pakastin/deck-of-cards  
  https://deck-of-cards.js.org/  
  **King of Hearts alone is 69 KB** : https://deck-of-cards.js.org/faces/1_13.svg

- CSS only (no Court images) (last commit: 2012)  
  https://github.com/zachwaugh/Helveticards
- PNG card background image = https://bfa.github.io/solitaire-js/img/card_back_bg.png
- [Google Images playingcards](https://www.google.com/search?q=old+52+cards&tbm=isch&tbs=rimg:CQvmkLdr_14McIjgYvxv84K-eaVXk-0nLcJFF3OanFgQriEXAiZjXEp9zM2hJ2fYh1rUdAmXW8kROLnUlky-kQYhn7SoSCRi_1G_1zgr55pEZomC09EhU8oKhIJVeT7SctwkUURF50UBpuCFl0qEgnc5qcWBCuIRRGBNOuJrmaMECoSCcCJmNcSn3MzESHqEP4mrUbzKhIJaEnZ9iHWtR0R9s1Zi32qMiwqEgkCZdbyRE4udRFP-xbZjpVQIioSCSWTL6RBiGftEX2c9kdcxbzu&tbo=u&sa=X&ved=2ahUKEwjCgrW0x6nhAhXCDOwKHbHpDiIQ9C96BAgBEBs&biw=1920&bih=947&dpr=1#imgrc=GL8b_OCvnml8hM:)

- DeckOfCards API - http://deckofcardsapi.com/

- Solitaire

  - Redux,React, the lot https://codepen.io/HunorMarton/details/rwpGXj

  - (2017) No frameworks/library No drag drop, PNG images for courts
    https://bfa.github.io/solitaire-js/  
    https://github.com/bfa/solitaire-js

- Poker API - https://rapidapi.com/danielamitay/api/poker-odds

#### SVG

- SVGO GUI - https://jakearchibald.github.io/svgomg/
- http://www.petercollingridge.appspot.com/svg-editor
- https://tympanus.net/codrops/2019/01/15/svg-filters-101/
- SVG minification and GZIP - https://blog.usejournal.com/of-svg-minification-and-gzip-21cd26a5d007
- https://css-tricks.com/gotchas-on-getting-svg-into-production/
- https://stackoverflow.com/questions/18467982/are-svg-parameters-such-as-xmlns-and-version-needed
- https://codepen.io/tigt/post/optimizing-svgs-in-data-uris

#### LZMA compression

- http://lzma-js.github.io/LZMA-JS/demos/advanced_demo.html
- https://github.com/LZMA-JS/LZMA-JS
- https://dafrok.github.io/gzip-size-online/
- Analyze GZ compression:  
  https://encode.ru/threads/1889-gzthermal-pseudo-thermal-view-of-Gzip-Deflate-compression-efficiency
  ![](https://i.imgur.com/J78H3LU.jpg)

#### Chess

Yes, I did https://chessmeister.github.io

`<img is=white-queen at=D5>`

- https://commons.wikimedia.org/wiki/Category:SVG_chess_pieces/Maurizio_Monge
- https://codepen.io/jeansarlon/pen/WpZNda/
- https://ilhooq.github.io/svgchessboard/demo/
- https://rexxars.github.io/react-chess/

### Code Fragments

Load SVG content in main document:

```
  <iframe src="file.svg" onload="this.before(this.contentDocument.children[0]); this.remove();"></iframe>
```

<hr>
<hr>
Published: 2020-08-06 17:13 
