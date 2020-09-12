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

3. **Disable user zooming:**

   - Add the `user-scalable=no` property to the HTML's `meta` tag.

     ```html
     <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
     ```

4. **Import a script to your HTML file:**

   ```html
   <script src="js/script.js"></script>
   ```

   

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
    
15. **Disable tap highlight & outline on mobile devices:**

    - Mobile browsers (Chrome and apparently Safari) highlight elements on clicking. Use these to disable them:

      ```css
      button {
      	-webkit-tap-highlight-color: transparent; // removes blue filter overlay
      	outline: none; // removes border-like outline
      }
      ```

    - **DISCLAIMER:** This is apparently bad for user accessibility because a.) without visual feedback, the user perception is that the app is slower (collimarco, Stack Overflow, https://stackoverflow.com/questions/21003535/anyway-to-prevent-the-blue-highlighting-of-elements-in-chrome-when-clicking-quic) and b.) it is important for users not using a mouse or those with visual impairments (http://www.outlinenone.com/). **USE AN ALTERNATE STYLING WHEN DISABLING**, such as `background-color: $new-color;` to signify feedback.

# SASS Stuff

1. **SASS Mixins:**

   - These act like functions in OOP languages. These do not have a return value. Just call them and they'll apply a style.

   ```css
   @mixin functionName($parameter){
     property: $parameter;
   }
   ```

2. **SASS Structuring:**
   - 'Base' folder
     - _globals.scss
     - _mixins.scss
     - _queries.scss
     - _resets.scss
     - _typography.scss
     - _variables.scss
   - 'Components' folder - for containers and individual components 
     - _header-container.scss
     - _main-container.scss
     - _footer-container.scss
   - 'Layout' folder - for semantic tags
     - _body.scss
     - _header.scss
     - _main.scss
     - _footer.scss
   - main.scss - import everything (put queries last)

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

   - **Splice (remove):** allows removal of element from a given index

     ```js
     myArray.splice(i, 1); // where i is the index, 1 is the amount of elements to remove starting from the index
     ```

   - **Splice (insert):** allows adding of elements at a given index

     ```js
     myArray.splice(i, 0, "hello"); // removes 0 elements, and adds the element "hello" at index i 
     ```

   - **To clear an array:**
     - Use `myArray.length = 0` instead of `myArray = []`.
     - This is perfect if you don't have **references to the original array `myArray`** anywhere else because this actually creates a brand new (empty) array. You should be careful with this method because if you have referenced this array from another variable or property, the original array will remain unchanged. Only use this if you only reference the array by its original variable `myArray`.  (Philippe Leybaert, Stack Overflow, https://stackoverflow.com/questions/1232040/how-do-i-empty-an-array-in-javascript)

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

5. **Equality:**

   - **'==':**

     - Is what JS uses to compare/work on variables with different data types through *type coercion* (matching data types with each other).

       - Its **inequality** counterpart is the '!='
       
       ```js
       "3" == 3 // true, despite string and int comparison
       1 == '1' // true, despite int and char comparison
       ```

   - **'===':**

     - Is what JS uses for **strict equality**, which means variables being tested are not converted into a common type.

       - Its **strict inequality** counterpart is '!=='
       
       ```js
       3 === 3 // true, because both are of the type number
   3 === '3' // false, because one is a number and the other is a string
       ```

6. **JS Objects:**

   - Contain properties and their values.

   - **Do not use semicolons**. Use commas instead, and omit on the last property.

     ```js
     var myDog = {
     	"name": "Kobi",
     	"legs": 4,
     	"friends": ["Minggay", "Jappy"],
         "favorite food": "Chicken"
     }
     ```

   - Properties can be called, but those with spaces need to use square bracket notation.

     ```js
     myDog.name; // returns "Kobi"
     myDog["favorite food"]; // returns "Chicken"
     ```

   - To change the values of properties, simply reassign them like variables.

     ```js
     myDog.name = "Clifford"; // replaces "Kobi" with "Clifford"
     ```

   - To add a property to an existing object, do like above but use a non-existing property.

     ```js
     myDog.bark = "Woof woof!"; // adds the "bark" property to myDog
     ```

   - To delete a property from an object, use the `delete` keyword.

     ```js
     delete myDog.bark;
     ```

   - To check if an object has a specific property, use the `hasOwnProperty()` method.

     ```js
     myDog.hasOwnProperty("friends"); // returns true
     ```

   - To check if an object has a specific value, use `Object.values(obj).includes(var)`

     ```js
     petOwnersAndDogs = {"John": "Charlie", "Jane": "Max"};
     
     var doIKnowThisDog = Object.values(petOwnersAndDogs).includes("Charlie"); //returns true
     ```

     

7. **Complex Objects:**

   - Nested objects' properties can be accessed by using the bracket notation.

     ```
     var student = {
     	1001: {
     		"name": "John Doe",
     		"year": 2,
     		"gender": "male",
     		"friends": ["Jane Doe", "Mark Zuckerberg"]
     	},
     	1002: {
     		"name": "Jane Doe",
     		"year": 3,
     		"gender": "female",
     		"friends": ["Tony Stark"]
     	},
     }
     
     console.log(student[1001]["gender"]); // returns male
     student[1001]["gender"] = "female"; // changes it to female
     ```

   - *If there is no array, add an array:*

     ```js
     student[1002]["friends"] = student[1002]["friends"] || [];
     // If there is an existing array, keep it. If there is none, initialize a new array (through || []).
     student[1002]]["friends"].push("John Doe");
     console.log(student[1002]["friends"]); // returns Tony and John
     
     // Why not student[1002]["friends"] = []? Because doing so will delete and reset the existing value/array stored already.
     ```

8. **Convert Number Systems:**

   - To convert, for example, a binary number to an integer:

     ```js
     parseInt("10011", 2); // returns 19
     ```

   - The second parameter, 2, signifies the *radix* or the base number. 8 signifies octal, 10 signifies decimal. Refer to the *list of numeral systems* (https://en.wikipedia.org/wiki/List_of_numeral_systems) for more information. 

9. **Conditional Statements:**

   - For a compact if-else statement, use the **conditional statement.**

   - `condition ?  return if true : return if false`

     ```js
     console.log(5 === 2 ? "It is equal" : "It is not equal"); // Prints "It is not equal"
     ```

10. **Accessing an HTML element in Javascript:**

    - Referred to as **Document Object Model (DOM)**.

    - Similar to how game dev environments handle their objects (parent-child hierarchal relationships).

      ```html
      <p id="my-text">This is my text!</p>
      
      <script type="text/javascript">
      	var myTextValue = document.getElementById("my-text").innerHTML;
      </script>
      ```

    - The `.getElementById("my-text")` specifies which element is being specified, hence IDs are only truly meant for specifying elements.

    - The `.innerHTML` property used in the example grabs whatever is **between the tags**, and stores it in the `var myTextValue` variable.

      - "DOM manipulations using `innerHTML` are slower and more failure-prone than manipulations based on individual DOM objects" (Michael Borgwardt, Stack Overflow, https://stackoverflow.com/questions/4879066/what-innerhtml-is-doing-in-javascript). For a better way of getting text, use the `.textContent` property instead.

        ```js
        var myTextValue = document.getElementById("my-text").textContent;
        ```

11. **Convert String to a char array:**

    - JS doesn't have chars, but fortunately there's an `Array.from()` function which allows String to char array conversions. This allows easy string manipulations.

      ```js
      var myString = "Hey";
      var myArray = Array.from(myString);
      
      console.log(myArray); // returns ['H', 'e', 'y']
      ```

    - There is also the `myString.split("")` function.

      ```
      myArray = myString.split("");
      console.log(myArray); // returns the same array as above
      ```

      

12. **Convert char array to String:**

    - After manipulating the char array, you would want to return it into a String.

      ```
      var myString2 = myArray.join(""); // returns "Hey"
      
      // No parameters returns the string with ',' between characters.
      
      var myString = myArray.join(); // returns "H,e,y"
      ```

13. **Adding an event listener:**

    - Note: do not include parentheses on the function call because it would mean you are invoking it immediately rather than referencing it.

      ```js
      document.getElementById("myElement").addEventListener("click", myFunction);	
      ```

14. **To know which element was triggered through addEventListener:**

    - Use the the `event` object and use its `target` property. Then use the `id` property to get its ID.

      ```js
      document.getElementById("myElement").addEventListener("click", myFunction);
      
      function myFunction() {
      	console.log(event.target.id); // returns the id of the triggered element
      }
      ```

15. **Give every element in a class an event listener:**

    - ```js
      Array.from(document.getElementsByClassName("myElements")).forEach(function(element) {
          element.addEventListener('click', functionToCall);
      });
      
      // Creates an array from every element with class "myElements", then executes a forEach loop, with a function that passes every element. Each individual element is then added an event listener, leading to a function.
      
      // Bonus chained code:
      
      function functionToCall() {
      	console.log(event.target.id); // Returns the id of the triggered element under the class "myElements"
      }
      ```

16. **Use ASCII characters in JS:**

    - Use the `String.fromCharCode()` function

      ```js
      var myChar = String.fromCharCode(69); // accepts a decimal value
      console.log(myChar); // returns 'E'
      ```

17. **Easily track variables on console:**

    - Use curly braces between the variable calls.

      ```
      var var1 = 1;
      var var2 = 2;
      
      console.log({var1, var2}); // returns {var1: 1, var2: 2}
      ```

18. **Check if array includes a certain value:**

    - *or* checking if a value is present in an array

    - **NOTE:** object counterpart is `.hasOwnProperty()`
    
      ```js
      var myArray = ["a", "b", "c"];
      var varToCompare = "a";
      
      return myArray.includes(varToCompare); // returns true
      ```

19. **Join Strings together:**

    - Use the `.concat()` method

      ```js
      var str = "Hello ";
      var str2 = "world";
      console.log(str.concat(str2)); // returns "Hello world"
      ```

20. **Get the data type of a given variable:**

    - Use the `typeof()` method

      ```js
      console.log(typeof("Hello world!")); // returns String
      ```

21. **Passing arrays (and objects?) pass references, not values:**

    - Only works on arrays and objects (?), variables are safe. (phew)

      ```JS
      var myArray1 = ["Dog", "Cat"];
      var myArray2 = myArray1;
      
      myArray1.push("Bird");
      
      console.log(myArray2); // returns ["Dog", "Cat", "Bird"]
      
      var myNum1 = 1;
      var myNum2 = 2;
      
      myNum2 = myNum1;
      
      myNum1 = 3;
      
      console.log(myNum2); // returns 1 :-D
      ```

    - To get around this, use the `slice()` function

      ```js
      var clone = original.slice(0);
      ```

    - Reference: https://stackoverflow.com/questions/14491405/javascript-passing-arrays-to-functions-by-value-leaving-original-array-unaltere

22. **Parse Integer and To String Methods:**

    - Use `parseInt()` to turn String into a number

      ```js
      var myNumber = parseInt("23");
      
      console.log(myNumber); // returns 23
      ```

    - Use `toString()` to turn number into String

      ```js
      var myString = myNumber.toString();
      
      console.log(myNumber); // returns "23"
      ```

      