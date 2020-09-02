>>> VIEW LIVE SERVER ON OTHER DEVICES: <<<
 - Connect devices to same network
 - cmd then ipconfig on host computer
 - Get the IPV4 address of the host computer
 - Type the following into any device's browser: http://[IPV4]::5500

>>> CSS FRESH TEMPLATE <<<

* {
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
}

body, html {
  height: 100%;
  margin: 0;
  padding: 0;
  font-size: 62.5%;
}

>>> FIX FOR 1440P, 2K RESOLUTION <<<
 - Just set font-size back to 100% (16px) or 

>>> SEPARATE LITERAL AND CONTENT CONTAINER <<<
 - Separate so you have more control over the content's margin and padding
 - ex. .card -> .content-container -> .content-txt & .content-img

>>> SVG OVERLAY COLOR <<<

svg path {
  fill: white;
}

[[[[[[[[[[[[ EXPLANATION ]]]]]]]]]]]]]]

 - height: 100%; //to define site height (every child follows this measure)
 - marign: 0%; //to remove margining caused by height: 100% (the html pushes body down)
 - box-sizing: border-box; //includes padding and border to an element's height and width (no stretching when adding padding)
 - font-size: 62.5% //to make the originally (universal) 16px default font size to 10px, which is easier to manipulate and calculate when using font-based units (em and rem)

>>> MEDIA QUERIES - SEPARATE STYLING FOR SCREEN/HANDHELD: <<<

<link rel="stylesheet" media="screen" href="style.css" type="text/css" />
<link rel="stylesheet" media="handheld" href="mobile.css" type="text/css" />

>>> PAGECDN EASYFONTS - IMPORT ALL GOOGLE FONTS AT ONCE: <<<

<link href="https://pagecdn.io/lib/easyfonts/fonts.css" rel="stylesheet" />

BACKGROUND IMAGE PROPERTIES MNEMONICS: ARPS

>>> CENTER A DIV - FLEXBOX: <<<

body, html {
  height: 100%: //define height of body & html (according to viewport)
  //100% on top container is same as 100vw and 100vh
}

div .container {
  display: flex; //apply flexbox
  justify-content: center; //center horizontally
  align-items: center; //center vertically
}

>>> CENTER A DIV - BLOCK: <<<

div .container {
  display: block;
  margin: 0 auto;
}

>>> USE PADDING WITHOUT AFFECTING SIZE - BORDER-BOX: <<<
* { 
  -moz-box-sizing: border-box; 
  -webkit-box-sizing: border-box; 
  box-sizing: border-box; 
}

>>> GRADIENT: <<<
.box {
  background-image: linear-gradient(to right, red, blue);
}

>>> CALCULATE PROPERTY: <<<
.tocalc {
  width: calc(100% - 20px);
}

>>> MAKE DIV AS BIG AS ITS CONTENTS - INLINE: <<<
div {
  display: inline;
  //OR
  display: inline-block;
  //OR
  display: inline-flex;
}

>>> CSS VARIABLES: <<<

div {
  --color: red; //store value as "--color"
  background-color: var(--color); //set background color same as color property
}

>>> BLOCK VS. INLINE <<<
 - BLOCK: Has a width by default, usually 100% of the parent's width
 - INLINE: The width is dependent on the size of its content

>>> REPONSIVE, BUT FIXED TEXT (DOES NOT RE-ADJUST) <<<
 - font-size: 10vw;

>> TO HAVE TEXT THAT DOES NOT WRAP ON RESIZE <<<
 - Set a width for it: width: 17rem; //still checking if it should be rem or any type works

>>> GOOD DIV SIZE (MOBILE) <<<
 - 300px (30rem on 62.5%) -- good size while still ok for 320px devices

>>> (SASS) FUNCTIONS (NO RETURN VALUE <<<
@mixin functionName($parameter){
  property: $parameter;
}

>>> HAVE INPUT, TEXTAREA AND BUTTON INHERIT UNIVERSAL FONT <<<

input, textarea, button {
  font-family: inherit;
}

>>> CHROME DEVICE TOOLBAR SIMULATE ZOOM <<<
 - shift + drag

>>> BUTTON ANIMATIONS (disclaimer: SASS var syntax) <<<

button {
  transition: color .5s, background-color .5s;
}

button:hover {
  color: $newcolor;
  background-color: $newbackground;
}

>>> TYPES OF SCALING FOR RESPONSIVE DESIGN <<<
 - SET WIDTH: Does not change the div size (doesn't wrap text), HOWEVER NEEDS TO BE OPTIMIZED FOR SMALLEST SCREEN AVAILABLE (320px) -- good for text that needs to be in a particular order
 - SET MARGIN: Automatically changes div size depending the screen size (text is automatically wrapped)

>>>>>>>>>>>>>>>>>>>> VSCODE SHORTCUTS <<<<<<<<<<<<<<<<<<<<

>>> DUPLICATE SELECTION <<<
 - Upwards: Shift + Alt + Up
 - DownwardS: Shift + Alt + Down

>>> SELECT CURRENT LINE <<<
 - Ctrl + L

>>> COMMENT SELECTION <<<
 - Ctrl + K + C	
