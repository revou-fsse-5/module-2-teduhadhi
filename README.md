# 🦆 BORED DUCK

[First Module](https://revou-fsse-5.github.io/module-1-teduhadhi/)

[Second Module](https://revou-fsse-5.github.io/module-2-teduhadhi/)



## General

Turns out being bored is not necessarily a bad thing??
<br>

This is a simple page about a certain bored duck looking for a company while explaining some good things about being bored.

# V.02-02

## Dark Mode (Beta)

Dark mode feature using javascript

1. Adding a button with onclick attribute


```html
<button onclick="darkMode()" class="button-test">dark-mode</button>
```

2. Declare and select the elements.
3. Retrieve current state using localStorage.
4. Using if else to change the state of the elements and the localStorages value when the button is activated.

```js
var element = document.body;
var element2 = document.getElementById("youtube");

element.classList.toggle(localStorage.dark);          
element2.classList.toggle(localStorage.dark);

function darkMode() {
    
    if (localStorage.dark !="dark-mode"){
    element.classList.toggle("dark-mode",true);          
    element2.classList.toggle("dark-mode",true);
    localStorage.dark="dark-mode"
    }

    else{
    element.classList.toggle("dark-mode",false);          
    element2.classList.toggle("dark-mode",false);
    localStorage.dark=""
    }  
};
```
5. Set the css properties for the activated toggle.

```css
.dark-mode{
    filter: invert(100%);
    background-color: black;
}
```

<img src= "sources\readme\m2-dark-1.png" alt="dark mode 1"> <br>

<img src= "sources\readme\m2-dark-2.png" alt="dark mode 2">

*Issue : the nav bar behaviour changes when the page is on dark-mode (the position no longger fixed and the width changes to the body's width)
---

<br>

# V.02-01

Task
1. Applying **custom font** using @font-face or embed
2. Applying **text-shadow** to text and **list-style** to the list
3. Applying 1 **responsive background image**, (using contain or cover, suit your needs)
4. Applying 1 **responsive image** with **picture + source + srcset** method
5. Creating one **Asymmetrical Grid** → layouting grid, both container and item (children)
6. Creating simple **animation** with two methods: animation and transition

## Custom Font
## text-shadow and list-style
- text-shadow

Adding shadow when hovering cursor over the texts

```css
.side-items{
    text-decoration: none;
    margin-top: 5px;
    transition: font-weight 0.2s, font-size 0.2s;
    
    &:visited{
        color: white;
    }

    &:link{
        color: white;
    }

    &:hover{
        text-shadow: 4px 4px 3px black;
    }
}
```

<img src= "sources\readme\m2-list-2.png" alt="m2-list-2">

<br>

- list-style

Creating dash "-" list-style by removing the bullet points then adding "-" using pseudo element.

```css
.list-style{
    list-style: none ;
    padding: 0;
    padding-left: 15px;
    margin: 0;
    margin-top: 10px;
    font-size: 15px;
    font-weight: 400;
    
    li{
        margin-top: 5px;
    }

    li:before{
        content: "- ";
    }
}
```

<img src= "sources\readme\m2-list-1.png" alt="m2-list-1">

## Responsive Background Image

Responsive background image by mirroring the background using transform.

```css
.pms-right{
    grid-area: mnimg;
    text-align: center;
    height: 100%;
    width: 100%;
    background-image: url(../sources/images/main-image.svg);
    background-size: cover;
    background-position-x:-33px;
    animation: 0.75s ease-in-out fade-in 0.5s;
    animation-fill-mode: forwards;
    opacity: 0;
}

...

@media (max-width :840px){
    .main-sect{
        display: grid;
        grid-template-columns: 1fr;
        grid-template-areas:
        "mnimg"
        "mnttl";
    }
    .pms-right{
        height: 500px;
        background-position: center;
        background-size: contain;
        background-repeat: no-repeat;
        transform: scaleX(-1);
    }
}
```

<img src= "sources\readme\m2-bg-1.png" alt="m2-bg-1">
<img src= "sources\readme\m2-bg-2.png" alt="m2-bg-2">

## Responsive Image (srcset)

Responsive image using srcset

```css

...

<picture class="box-first">
    <source media="(min-width:950px)" srcset="sources\images\grid-1.jpg">
    <img class="boxes box-first" src="sources\images\grid-6.jpg">
</picture> 

...

```

<img src= "sources\readme\m2-srcset-1.png" alt="m2-srcset-1">
<img src= "sources\readme\m2-srcset-2.png" alt="m2-srcset-2">



## Asymmetrical Grid

Using basic grid-area

```css
.main-grid{
    display:grid;
    grid-template-columns: repeat(4,1fr);
    grid-template-rows: repeat(3,200px);.
}

...

.box-first{
    grid-area : 1/1/3/2;
    border-radius: 1em 1em 5em 1em;
}

...

```

<img src= "sources\readme\m2-grid-1.png" alt="m2-grid-1">

Using overflow:scroll to minimize space's usage.

```css
    @media(max-width:900px){
        grid-template-columns: repeat(2,1fr);
        grid-template-rows: repeat(4,200px);
        height: 400px;
        overflow-y: scroll;
        scrollbar-width: none;
    }
```

<img src= "sources\readme\m2-grid-2.png" alt="m2-grid-2">


<br>

Using grid-template-area

```css
.data-sub-cont{
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 20px 15px;
    grid-template-areas:
    "dtnme dtnme dtnme dteml dteml dteml"
    "dtaddr dtaddr dtaddr dtaddr dtaddr dtaddr"
    "dtcty dtcty dtpvn dtpvn dtpst dtpst"
    "dtchk dtchk dtchk dtchk dtchk dtchk"
    "dtrdo dtrdo dtrdo dtrdo dtrdo dtrdo"
    "dttxt dttxt dttxt dttxt dttxt dttxt"
    "dtsmt dtsmt dtsmt dtsmt dtsmt dtsmt";

    ...

    .data-name{
    grid-area: dtnme;
}
.data-email{
    grid-area: dteml;

    ...
}
}
```

Responsive grid layout

<img src= "sources\readme\m2-grid-3.png" alt="m2-grid-3">

```css
@media (max-width:600px) {
    .data-sect{
        font-size: 0.9em;
    }
    .data-sub-cont{
        display: grid;
        grid-template-columns: 1fr;
        gap: 20px 15px;
        grid-template-areas:
        "dtnme"
        "dteml"
        "dtaddr"
        "dtcty"
        "dtpvn"
        "dtpst"
        "dtchk"
        "dtrdo"
        "dttxt"
        "dtsmt";
    }
}
```

<img src= "sources\readme\m2-grid-4.png" alt="m2-grid-4">

## Animation
- Animation

```css
.pms-right{
    grid-area: mnimg;
    text-align: center;
    height: 100%;
    width: 100%;
    background-image: url(../sources/images/main-image.svg);
    background-size: cover;
    background-position-x:-33px;
    animation: 0.75s ease-in-out fade-in 0.5s;
    animation-fill-mode: forwards;
    opacity: 0;
}

.bored-duck-text{
    margin: 0;
    font-size: 16px;
    line-height: 22px;
    font-weight: 400; 
    animation: 1.25s ease-out fly-in;
}

@keyframes fly-in{
    from{
        opacity: 0;
        translate: 0 50%;
    }
    to{
        opacity: 1;
        translate: 0 0;
    
    }
}

@keyframes fade-in{
    from{
        opacity: 0;
    }
    to{
        opacity: 1;
    }
}

```

<img src= "sources\readme\m2-an.png" alt="m2-an">

<br>

- Transition
    - hover

    Pop up hover

    <img src= "sources\readme\m2-tr-h-1.png" alt="m2-tr-h-1">
    <img src= "sources\readme\m2-tr-h-2.png" alt="m2-tr-h-2"><br><br>

    Shadow hover

    <img src= "sources\readme\m2-tr-h-3.png" alt="m2-tr-h-3">
    <img src= "sources\readme\m2-tr-h-4.png" alt="m2-tr-h-4"><br><br>

    Shadow hover

    <img src= "sources\readme\m2-tr-h-5.png" alt="m2-tr-h-5">
    <img src= "sources\readme\m2-tr-h-6.png" alt="m2-tr-h-6"><br><br>

    Opacity and Shadow hover

    <img src= "sources\readme\m2-tr-h-7.png" alt="m2-tr-h-7">
    <img src= "sources\readme\m2-tr-h-8.png" alt="m2-tr-h-8"><br><br>

    - focus

```css
input:focus,
select:focus,
textarea:focus {
    background-color: rgb(241, 241, 241, 0.15);
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.15);
}
```


 <img src= "sources\readme\m2-tr-f.png" alt="m2-tr-f">

 ---

 <br> 

# V.01-02

## Animation

Cast a shadow around the button element when the cursor hovering the button.

```css
.get-bored-button{
    margin-top: 20px;
    background-color: rgba(0, 0, 0, 0.15);
    border-style: none;
    color: rgb(255, 255, 255);
    border-radius: 30px;
    cursor: pointer;
    padding: 15px 26px;
    font-weight: 600;
    font-size: 15px;
    transition: box-shadow 0.15s;
}

.get-bored-button:hover{
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.15);
}
```

<img src= "sources\readme\hover-1.png" alt="hover-1">
<img src= "sources\readme\hover-2.png" alt="hover-2">

Cast a shadow around the input element when the input form being selected

```css
input,
select,
textarea {
    height: 35px;
    border-radius: 10px;
    border: 1px solid lightgray;
    font-size: 1em;
    padding-left: 10px;
    transition: background-color 0.15s;
    transition: box-shadow 0.15s;
}

input:focus,
select:focus,
textarea:focus {
    background-color: rgb(241, 241, 241, 0.15);
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.15);
}
```
<img src= "sources\readme\animation-active-1.png" alt="animation-active-1">
<img src= "sources\readme\animation-active-2.png" alt="animation-active-2">


## Responsive Layout

Using media query to create a responsive layout. The layout changes to the alternate styles, depends on the rules that have been set.

The changes of the grid layout and the other styles on the data section, when the screen resolution is set below 600px.

```css
.data-sect{
    margin: 200px 30px 0px ;
    max-width: 980px;
    padding: 0 5%;
    font-size: 15px;
}
.data-sub-cont{
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 20px 15px;
    grid-template-areas:
    "dtnme dtnme dtnme dteml dteml dteml"
    "dtaddr dtaddr dtaddr dtaddr dtaddr dtaddr"
    "dtcty dtcty dtpvn dtpvn dtpst dtpst"
    "dtchk dtchk dtchk dtchk dtchk dtchk"
    "dtrdo dtrdo dtrdo dtrdo dtrdo dtrdo"
    "dttxt dttxt dttxt dttxt dttxt dttxt"
    "dtsmt dtsmt dtsmt dtsmt dtsmt dtsmt";
}


@media (max-width:600px) {
    .data-sect{
        font-size: 0.9em;
    }
    .data-sub-cont{
        display: grid;
        grid-template-columns: 1fr;
        gap: 20px 15px;
        grid-template-areas:
        "dtnme"
        "dteml"
        "dtaddr"
        "dtcty"
        "dtpvn"
        "dtpst"
        "dtchk"
        "dtrdo"
        "dttxt"
        "dtsmt";
    }
    .select-check-radio{
        display: flex;
        row-gap: 15px;
        flex-direction: column;
    }

    .radio-check{
        height: 17px;
        width: 34px;
    }
}
```

<img src= "sources\readme\section-3.png" alt="section-3">
<img src= "sources\readme\cell-sect3.png" alt="cell-section-3">

## Hamburger Button

Using **popover** value to create a hamburger button

Then using **translate** attribute to create a side-in animation.

```html
<button popovertarget="side-menu" class="menu-button"><img class="profile-icon" src="sources\icons\menu-icon.svg">
</button>

<nav class="side-menu" popover role="side-menu" id="side-menu">
        <button popovertarget="side-menu" popoevertargetaction="hide" class="menu-button"><img class="left-icon" src="sources\icons\left-icon.svg">
        </button>
        <ul class="side-list">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Help</a></li>
        </ul>
    </nav>
```

```css
.side-menu{
    position: fixed;
    right: auto;
    border: none;
    color: white;
    padding-top: 30px;
    padding-left: 11px;
    height: 100vh;
    width:150px;
    background-color: rgb(0, 0, 0);
    translate: -100% 0;
    transition: translate 0.5s, display 0.5s ease-out allow-discrete;
    z-index: 3;
}
 
.side-menu:popover-open{
    translate: 0 0;

        @starting-style{
            translate: -100% 0;
        }
}
```

<img src= "sources\readme\cell-hmbrgr1.png" alt="cell-hamburger-1">
<img src= "sources\readme\cell-hmbrgr2.png" alt="cell-hamburger-2">

---

<br>

# V.01-01

### Main Layout
Here is the general concept about the layout

<img src= "sources\readme\layout.png" alt="layout">

### Head

&lt;meta> set the meta tags for the metadatas.

```html
    <meta name="keywords" content="Boredom, Mindfulness, Duck">
    <meta name="description" content="Turns out being bored is not that all bad and here are some of the good sides of boredom.">
    <meta name="author" content="Teduh Adhi">
```
## Sections

### Navigation
Building the navigation section using &lt;nav> tag to define the navigation's semantic tag.

Make the navigation bar stick on the top of the page using &lt;position> with **fixed** value, then set the **z-index** value higher than the default value.

Using **flexbox** to spread the element, divides the navigation into three section (left, middle and right), then create a sub division inside of the sections (nested layout concept).

Added pop up animation when the cursor hovering above the icons.

```html
<div class="container">
    <img class="cart-icon" src="sources\icons\cart-icon.svg">
    <div class="popup">Cart</div>
</div>
```

```css
.container .popup{
    position: absolute;
    background-color: gray;
    color: white;
    padding-top: 4px;
    padding-bottom: 4px;
    padding-left: 8px;
    padding-right: 8px;
    border-radius: 2px;
    font-size: 12px;
    bottom: -30px;
    opacity: 0;
    transition: opacity 0.15s;
    pointer-events: none;
    white-space: nowrap;
}

.container:hover .popup{
    opacity: 1;
}
```


<img src= "sources\readme\navigation.png" alt="nav">


### First Section

Using **&lt;display> : grid;** to create the layout:

```css
.main-sect{
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin: 0px 30px;
    gap: 20px;
    align-items: center;
    grid-template-areas:
    "mnttl mnimg";
}
```

Using &lt;h1> and &lt;p> tags to respectively define the title and paragraph semantic tag.

Using &lt;button> tag to set up a clickable button.

Using &lt;img> tag to attatch an image.

```html
<img class="main-image" src="sources\images\main-image.svg">
```

<img src= "sources\readme\section-1.png" alt="section-1">

### Second Section

Using &lt;h2> tag to define the second heading.

Using &lt;ul> and &lt;il> tags to respectively set an undordered list and the list items.

Using &lt;iframe> tag to embed a video.

```html
<iframe class="vsauce-boredom-video" src="https://www.youtube.com/embed/Qwd25JV-jnU?si=73oMtepE2-BSPKla?"allow="fullscreen"></iframe>
```

<img src= "sources\readme\section-2.png" alt="section-2">

### Data Section

Using a combination of **grid** and **flexbox** to create the layout.

Using &lt;form> and &lt;input> tags to respectively define form for user input and set a certain type of input.

Using &lt;select> and  &lt;option> tags to set up up dropdown select menu and the option items.

Using &lt;textarea> to set a textbox for user input.

```html
<input class="data-city" type="text" placeholder="City" name="submit-city" required> 
<select class="data-province" name="submit-province">
    <option value="EastJav">East Java</option>
    <option value="CentJaw">Central Java</option>
    <option value="WestJav">West Java</option>
</select>
```

<img src= "sources\readme\section-3.png" alt="section-3">

### Footer
Using &lt;footer> to define the footer's semantic tag.

<img src= "sources\readme\footer.png" alt="footer">

<br>
<br>
<br>

---

