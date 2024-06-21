# 🦆 BORED DUCK

[Link](https://revou-fsse-5.github.io/module-1-teduhadhi/)
# V.01
## General

Turns out being bored is not necessarily a bad thing??
<br>

This is a simple page about a certain bored duck looking for a company while explaining some good things about being bored.

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
# V.02

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