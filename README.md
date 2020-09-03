**P.S.** ~~These are all originally written in a .txt file so I can access it with Notepad, hence the Python converter script. Will probably look for a markdown viewer/editor soon.~~ Using Typora now! Looks pretty good. Hopefully it stays as my markdown editor for a while.

**P.P.S.** These will probably have wrong information in it. It still pays to be a good ~~programmer~~ coder and research. :-)

# General Knowledge Stuff

1. **VSCode Shortcuts:**
   - **Select current line:** Ctrl + L
   - **Comment selection:** Ctrl + K + C
   - **Uncomment selection:** Ctrl + K + U
   - **Duplicate selection (upwards/downwards):** Shift + Alt + Up / Shift + Alt + Down
   - **Enable word wrap on editor:** Alt + Z
   - **Show/hide current block:** Ctrl + K + L
2. **To view VSCode Live Server on Other Devices:**
   - Connect devices to the same network.
   - Open command prompt then execute *ipconfig* on the host computer.
   - Get the **IPV4** address of the host computer.
   - Type the following into any device's browser: http://**[IPV4]**::5500
     - e.g. http://192.168.1.204:5500
3. **Simulate zoom in Chrome's device toolbar:**
   - Shift + Drag Up/Down
   - Works in latest Microsoft Edge (and other Chromium-based browsers)

4. **Static vs. Dynamic typed languages:**

   - **Dynamically-typed languages**, such as **JavaScript** and **Python**, are languages where the data types of variables are only determined on run time. These are frequently referred to as *scripting languages*.

     ```js
     var myInt = 1; //assumes it is an int on runtime
     var myString = "Hello world!"; //assumes it is a String on runtime
     ```

   - **Statically-typed languages**, such as **C++** and **Java**, are languages where the data types of variables are explicitly stated during writing.

     ```java
     int myInt = 1;
     String myString = "Hello world!";
     ```

# HTML Stuff

1. **Adaptive CSS styling tags:**

   ```html
   <link rel="stylesheet" media="screen" href="style.css" type="text/css" />
   <link rel="stylesheet" media="handheld" href="mobile.css" type="text/css" />
   ```

   - Not recommended. This changes the styling depending on the device (think facebook.com and m.facebook.com). Better to just use responsive styling.

2. **CDN (Content Delivery Network) for all Google Fonts:**

   ```html
   <link href="https://pagecdn.io/lib/easyfonts/fonts.css" rel="stylesheet" />
   ```

   - Might not work in some instances. It didn't load on my phone when I viewed my site through Live Server. Had to manually select individual Google Fonts. 

# CSS Stuff

1. **Resets:**

   ```css
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
   ```

   - `box-sizing: border-box` allows margin and padding to be a part of a component's overall size *(this means the component no longer resizes when applying a margin/padding)*
   - `font-size: 62.5%` turns the font-size to 10px, which is much easier to calculate with when using font size-based measurements *(rem and em)*

2. **Easily adjust component sizes for 1440p, 4k:**

   - Set `font-size: 62.5%` to something larger, perhaps 100% or 20px.

3. **Separate literal and content container for more control**

   - This is to allow control over the content's padding and margin without setting them manually.
   - e.g. `.card -> .content-container -> .content-txt & .content-img`
     - .`card` handles size, `.content-container` handles padding/margins.

4. **Overlay an .svg file with a solid color (e.g. white):**

   ```css
   svg path {
     fill: white;
   }
   ```

5. **Mnemonics for `background-image` properties:**

   - **ARPS:** Attachment, Repeats, Position, Size

   ```css
   background-image: url("test.png");
   background-attachment: fixed;
   background-repeat: no-repeat;
   background-position: 0rem;
   background-size: 100% auto;
   ```

6. **Center an element:**

   - **Flexbox Method**

   ```css
   .container {
     display: flex; /*assuming you use flex-direction: row (default)*/
     justify-content: center; /*center horizontally*/
     align-items: center; /*center vertically*/
   }
   ```

   - **Margin Auto Method**

   ```css
   .container {
     display: block;
     margin: auto auto; /*applies equal margin to all sides*/
   }
   ```

7. **Apply gradient:**

   ```css
   .box {
     background-image: linear-gradient(to right, red, blue);
   }
   ```

8. **Calculate property:**

   ```css
   .tocalc {
     width: calc(100% - 20px);
   }
   ```

9. **Set div to only be as large as its contents:**

   ```css
   div {
     display: inline;
     //OR
     display: inline-block;
     //OR
     display: inline-flex;
   }
   ```

10. **CSS Variables:**

    ```css
    div {
      --color: red; /*store value as "--color"*/
      background-color: var(--color); /*set background color same as color property*/
    }
    ```

11. **Block vs. Inline:**

    - **BLOCK:** Has a height and width by default, usually 100% of the parent's height and width.
    - **INLINE**: The height and width is dependent on the size of its content.

12. **Have Input, TextArea, and Button elements inherit the universal font:**

    ```css
    input, textarea, button {
      font-family: inherit;
    }
    ```

13. **Simple Transitions:**

    - ***Disclaimer:** Has SASS syntax for the variables*

    ```css
    button {
      transition: color .5s, background-color .5s;
    }
    
    button:hover {
      color: $newcolor;
      background-color: $newbackground;
    }
    ```

    - Good for simple transitions like changing button and link colors.

14. **Types of scaling for Responsive Design:**

    - **Set Width:** Ensures a fixed width, will not adjust when screen size is larger/smaller (will have to double-check).
    - **Set Margin:** Resizes the div depending on the screen size. Pretty good as long as you pair it with `min-width` and `max-width` *(and its height counterparts).*

# SASS Stuff

1. **SASS Mixins**

   - These act like functions in OOP languages. These do not have a return value. Just call them and they'll apply a style.

   ```css
   @mixin functionName($parameter){
     property: $parameter;
   }
   ```

# JavaScript Stuff

1. **JAVASCRIPT VS. THE WORLD:**
   - Listed are a bunch of JS quirks that are different from other languages I've used:
     - **JavaScript has no 'char' datatype**
       - Data stored in single quotations ('hello') have the **string ** data type.
     - **JavaScript defines any numerical value as 'number'**
       - Floats, doubles, ints, are all defined as *'number'* in JS.

2. **Array Methods:**

   - **Pop:** removes the last element of an array (returns the element)

     ```js
     myArray.pop();
     ```

   - **Shift:** removes the first element of an array (returns the element)

     ```js
     myArray.shift();
     ```

   - **Push:** adds a new element to the end of the array (returns new length)

     ```js
     myArray.push("New last element");
     ```

   - **Unshift:** adds a new element to the beginning of the array (returns new length)

     ```js
     myArray.unshift("New first element");
     ```

3. **Accessing elements in nested arrays:**

   ```js
   var myArray = [["Eggs", 12], ["Milk", 1]];
   
   var howManyEggsShouldIBuy = myArray[0][1]; //2nd element of 1st parent element
   
   //returns 12
   ```

4. **Function variables:**

   ```js
   var myVar = 5;
   
   function myFunc() {
   	var myVar = 7;
   	//returns 7, does not override global myVar
   }
   
   function myOtherFunc() {
   	myVar = 2;
   	//returns 2, overrides the global myVar
   }
   ```

4. **Equality:**

   - **'==':**

     - Is what JS uses to compare/work on variables with different data types through *type coercion* (matching data types with each other).

       ```js
       "3" == 3 // true, despite string and int comparison
       1 == '1' // true, despite int and char comparison
       ```

   - **'===':**

     - Is what JS uses for **strict equality**, which means variables being tested are not converted into a common type.

       ```js
       3 === 3 // true, because both are of the type int
       3 === '3' // false, because one is int and the other is a char
       ```

       