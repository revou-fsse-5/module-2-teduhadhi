# 🦆 BORED DUCK
## Steps
### General

- Tags and Attributes 
    - Tags : define the function, usually placed at start.
    - Attributes : define the behaviour, also used for stylize the element.
```html
<input class="data-postal-code" type="text" pattern="[0-9]{5}" placeholder="Postal Code" name="submit-postalcode" required>
```

This is an example of how tags and attributes set up and work on html. **input** is the tag, used for the user to input data on the page. **class**, **type**, **pattern**, **placeholder**, **name** and **required** are the asstributes, used for set up certain behaviour to the element.

1. Set up a layout for the page.

<img src="sources\readme\layout.png" alt="layout">

2. Set up a **HTML** file.
    - Open **VSCode**.
    - Press **Ctrl + N**.
    - End the file name with **.html** to make a html file.
    - Open the file then type html, then selec **html: 5**.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```


3. Set up the &lt;meta> tags, for the metadatas of the HTML document.

```html
    <meta name="keywords" content="Boredom, Mindfulness, Duck">
    <meta name="description" content="Turns out being bored is not that all bad and here are some of the good sides of boredom.">
    <meta name="author" content="Teduh Adhi">
```
4. Set up the title icon and link.

```html
    <link rel="icon" type="image" href="sources\icons\duck-icon.png">
    <title>Bored as Duck</title>
```
5. Get font styles from [Google Font](!https://fonts.google.com/).
    - Search **Roboto** Font on Google Font.
    - Click **Get Font** button.
    - CLick **Get Embed Code**.
    - Select the particular Roboto font styles needed, there are 12 of them.
    - Copy then **Embed** the code.

```html
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700&display=swap" rel="stylesheet">
```

6. Set up the external link for the css files.
```html
    <link rel="stylesheet" href="styles/gen.css">
    <link rel="stylesheet" href="styles/nav.css">
    <link rel="stylesheet" href="styles/main-first.css">
    <link rel="stylesheet" href="styles/main-explained.css">
    <link rel="stylesheet" href="styles/main-data.css">
```
7. Set up the body to certain width and change the default font to Roboto. 
    - The Arial font is displayed when the Roboto font failed to load.
    - Margin to auto, that makes the body stay in the middle of the page.

```css
body {
    font-family: Roboto, Arial;
    margin: auto;
    padding-top: 120px;
    max-width: 980px;
}
```

#### Main Used Tags
- &lt;DOCTYPE html> : Specifies the version of HTML document.
- &lt;head> : Contains meta-infomration of the HTML document.
- &lt;meta> : Provides metadata about the HTML document.
- &lt;link> : Link external resources
- &lt;title : Sets the title of the HTML document.
- &lt;body> : Contains the content of the HTML document, displayed to user.
- &lt;main> : Semantic tag used to represent main content of the HTML document.
- &lt;nav> : Semantic tag to define the navigation content of the HTML document.
- &lt;section> : Semantic tag to define sections within the HTML document.
- &lt;h1>, &lt;h2> and &lt;h3> : Semantic tags represent the headings with each own level.
- &lt;p> : Semantic tag represent a paragraph.
- &lt;a> : Used to set up a hyperlink.
- &lt;button> : Set up a clickable button.
- &lt;input> : Set up an input field.
- &lt;img> : Attachs/embeds images to the HTML document.
- &lt;ul>, &lt;li> : Set up an unordered list and the list items.
- &lt;iframe> : Attachs/embeds an inline frame to the HTML document.
- &lt;form> : Defines form for user input.
- &lt;select>, &lt;option> : Set up dropdown select menu and the opstions.
- &lt;textarea> : Setup a textbox for user input.
- &lt;footer> : Semantic tag represents the footer of the HTML document.


### Navigation
<img src= "sources\readme\navigation.png" alt="nav">

1. Add **nav** tag to create navigation semantic tag.
2. Add a **class** attribute for stylize the element.
3. Add _"top-nav"_ **value** to the **nav** tag to diferentiate the element.
    - Set the navigation **height** attirbute to 55px.
    - Set the **display** to flexbox with flex value.
    - spread the content horizontally by set the **flex-direction** and **justify-content** to row and space-between.
    - Set **align-items** to center, that makes every element on the container aligned on their center.
    - Set the background color to white using **background-color**.
    - Set the bottom border width, style and color.
    - set the **position** to fixed position to make the element stay put on the window.
    - Set the **top**, **left** and **right** to 0, that makes the element stay at the top of the window.
    - Set the **z-index** higher than default, so the element placed on top of other element.
4. Make two horizontally distributed boxes contained the desired elements.
    - Set the **flex** attribute to 1, that makes the element fill the rest of the space.
    - Set the **display** attribute on the right section to flex in order to adjust the icons on the right section.
    - Set the **flex-shrink** to 0, so the space between the element remain the same when the window is smaller.

```html
<nav class="top-nav">
    <div class="left-nav-sect">
        ...
    </div>    
    <div class="right-nav-sect">
        ...
    </div>
```
```css
.top-nav {
    height: 55px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background-color: white;
    border-bottom-width: 1px;
    border-bottom-style: solid;
    border-bottom-color: rgb(228, 228, 228);

    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 2;
```
```css
.left-nav-sect{
    flex: 1;
    margin-left: 20px;
    margin-right: 20px;
}

.right-nav-sect{
    width: 450px;
    margin-right: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-shrink: 0;
}
```

5. Search bar and icons inside of the each section
    - Set the **class** to search-bar.
    - Set the **type** to text.
    - Set the **placeholder** to any desired text.
    - Set the **flex** to 1, that makes the search bar stretch when the window is expanded.
    - Set the **max-width** to 250px to limit the maximum width of the search bar.
    - Seth the **box-shadow** to inset to create shadows inside the search bar. Set the direction and the magnitude of the blurry effect of the shadows. Then set the color and the opacity of the shadows.
```html
<input class="search-bar" type="text" placeholder="Search">         
```
```css
.search-bar {
    flex:1;
    max-width: 250px;
    height: 26px;
    padding-left: 15px;
    font-size: 14px;
    border: 1px solid rgb(192, 192, 192);
    border-radius: 15px;
    box-shadow: inset 0px 0px 5px rgba(0, 0, 0, 0.05);
} 
```

6. Prepare the desired icons beforehand, it's better to have them in a single folder.
    - Set the image using **img** tag and **src** attribute to locate the icon file.
    - **div** ...-icon-container is used to make a pop-up messages.
    - Set the desired popup messages into the **popup** class **div** tag.
    - Set the **height**
    - Set the **cursor** to pointer, that makes the cursor change info pointer whenever it floats above the element.
    - Set the **...-icon-container** opacity to 0 to make the pop-up messages transparent.
    - Set the **...-icon-container .popup** **display** to flex, **justify-content** to center, **align-items** to center and **position** to relative to make the pop-up messages vertically aligned with each of the icons.
    - Set the **...-icon-container:hover .popup** opacity to 1 to make the pop-up messages show up when the cursor floats above the element, and set the bottom to desired position the pop-up messages.
```html
<div class="cart-icon-container">
    <img class="cart-icon" src="sources\icons\cart-icon.svg">
    <div class="popup">Cart</div>
</div>
```
```css
.cart-icon,
.envelope-icon,
.globe-icon,
.heart-icon,
.profile-icon {
    height: 24px;
    cursor: pointer;
}


.cart-icon-container,
.heart-icon-container,
.envelope-icon-container,
.profile-icon-container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}


.cart-icon-container .popup,
.heart-icon-container .popup,
.envelope-icon-container .popup,
.profile-icon-container .popup{
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


.globe-icon-container:hover .popup,
.cart-icon-container:hover .popup,
.heart-icon-container:hover .popup,
.envelope-icon-container:hover .popup,
.profile-icon-container:hover .popup{
    opacity: 1;
}
```

7. Create a button with icon (trial).
    - Between the **button** tag, set an **img** tag
    - Set the **background**, **border** and **padding** to none and 0 to show only the icon.
```html
<div class="profile-icon-container">               
    <button class="profile-button"><img class="profile-icon" src="sources\icons\profile-icon.svg">
    </button>
    <div class="popup">Sign In</div>                                         
</div> 
```
```css
.profile-button{
    background:none;
    border: none;
    padding: 0;
} 
```

### First Section : Title
<img src= "sources\readme\section-1.png" alt="section-1">

1. Set up the big container, then divde them into two side by side smaller container.
```html
<section class="main-sect">
    <div class="pms-left">
        ...
    </div>
    <div class="pms-right">
        ...
    </div>
</section>
```

2. Stylize both containers.
```css
.pms-left{
    border-radius: 20px;
    padding: 15px;
    background: linear-gradient(rgba(255, 255, 255, 1), rgba(251, 251, 251, 0.5) 100%), linear-gradient(90deg, #84d2ff, #8d5acd);
    height: 400px;
}

.pms-right{
    text-align: center;
}
```

3. For the left container, set up the title, the paragraph and the linked button then stylize them.
```html
<h1 class="bored-duck-title">BORED DUCK</h1>
<p class="bored-duck-text">In a serene pond, there lived a duck named Quackington, who was constantly plagued by boredom. Each day felt like a monotonous repetition of paddling lazily across the water and nibbling on aquatic greens. He longed for excitement to break the mundane routine, gazing wistfully at the sky for adventure to descend upon his feathered world.</p>
<a href="https://www.google.com/search?q=pizza&sca_esv=eae7a402c78866a8&sca_upv=1&udm=2&sxsrf=ADLYWIIDq30tfIXDuhL-qONOaqe2Tly-Nw%3A1718271965922&ei=3b9qZpzvN5ad4-EPtNexoAs&ved=0ahUKEwjc0Z_xpdiGAxWWzjgGHbRrDLQQ4dUDCBA&uact=5&oq=pizza&gs_lp=Egxnd3Mtd2l6LXNlcnAiBXBpenphMg0QABiABBixAxhDGIoFMgoQABiABBhDGIoFMggQABiABBixAzIFEAAYgAQyCBAAGIAEGLEDMggQABiABBixAzIFEAAYgAQyBRAAGIAEMgUQABiABDIFEAAYgARIsR1QhwpY8RtwBngAkAEAmAFboAHSBaoBATm4AQPIAQD4AQGYAg-gArsGwgIEECMYJ8ICBBAAGAPCAg4QABiABBixAxiDARiKBZgDAIgGAZIHBDEzLjKgB_wv&sclient=gws-wiz-serp" target="_blank">
<button class="get-bored-button">GET BORED</button>
</a>
```
 ```css
 .bored-duck-title{
    margin:0;
    font-size: 70px;
}
.bored-duck-text{
    margin: 0;
    font-size: 16px;
    line-height: 22px;
    font-weight: 400; 
}
```

<img src="sources\readme\hover-1.png" alt="hover-1">  <img src="sources\readme\hover-2.png" alt="hover-2">

```css
.get-bored-button{
    margin-top: 20px;
    background-color: rgba(0, 0, 0, 0.15);
    border-style: none;
    color: rgb(255, 255, 255);
    border-radius: 30px;
    cursor: pointer;
    padding-top: 15px;
    padding-bottom: 15px;
    padding-left: 26px;
    padding-right: 26px;
    font-weight: 600;
    font-size: 15px;
    transition: box-shadow 0.15s;
}

.get-bored-button:hover{
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.15);
}
```
4. For the right container, set up the image.
```html
<img class="main-image" src="sources\images\main-image.svg">
```
```css
.main-image{
    height: 350px;
}
```
### Second Section : Explained
1. Add **section** tag to create semantic tag
2. Make two horizontally distributed grid contained the desired elements.
    - Set the **display** attribute to grid
    - Set the **grid-template-columns** to 1fr 1fr, to make two equal width grids.
    - Adjust the **margin**, **column-gap** and **column-row** to desired number.
    - Set the **aligned-items** to center, that makes the element inside the grid vertically aligned at the middle.
    - Set the **text-align** center to make the content horizontally aligned at the middle.

```html
<section class="main-sect">
    <div class="pms-left">
        ...
    </div>
    <div class="pms-right">
        ...
    </div>
```
```css
.main-sect{
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-right: 30px;
    margin-left: 30px;
    column-gap: 20px;
    row-gap: 20px;
    align-items: center;
}
```
```css
.pms-left{
    border-radius: 20px;
    padding: 15px;
    background: linear-gradient(rgba(255, 255, 255, 1), rgba(251, 251, 251, 0.5) 100%), linear-gradient(90deg, #84d2ff, #8d5acd);
    height: 400px;
}

.pms-right{
    text-align: center;
}
```

2. Add **h1** tag to make a semantic title.
    - Set the **font-size** to adjust the font size of the title.
```html
 <h1 class="bored-duck-title">BORED DUCK</h1>
 ```
 ```css
 .bored-duck-title{
    margin:0;
    font-size: 70px;
}
```
3. Add **p** tag to make a semantic paragraph.
    - Set the **font-size** to adjust the font size of the parapgraph.
    - Set the **line-height** to adjust the spacing between the lines of the paragraph.
    - Set the **line-weight** to adjuts the thickness of the font.
```html
 <h1 class="bored-duck-title">BORED DUCK</h1>    
 ```html
<p class="bored-duck-text">In a serene pond, there lived a duck named Quackington, who was constantly plagued by boredom. Each day felt like a monotonous repetition of paddling lazily across the water and nibbling on aquatic greens. He longed for excitement to break the mundane routine, gazing wistfully at the sky for adventure to descend upon his feathered world.</p>
 ```
```css
.bored-duck-text{
    margin: 0;
    font-size: 16px;
    line-height: 22px;
    font-weight: 400; 
}
```

4. Add an **a** tag followed by **href** attribute then **button** tag, to make a linked button
    - Set **target** attribute to _blank, to make the link opened in a new tab.
```html
<a href="https://www.google.com/search?q=pizza&sca_esv=eae7a402c78866a8&sca_upv=1&udm=2&sxsrf=ADLYWIIDq30tfIXDuhL-qONOaqe2Tly-Nw%3A1718271965922&ei=3b9qZpzvN5ad4-EPtNexoAs&ved=0ahUKEwjc0Z_xpdiGAxWWzjgGHbRrDLQQ4dUDCBA&uact=5&oq=pizza&gs_lp=Egxnd3Mtd2l6LXNlcnAiBXBpenphMg0QABiABBixAxhDGIoFMgoQABiABBhDGIoFMggQABiABBixAzIFEAAYgAQyCBAAGIAEGLEDMggQABiABBixAzIFEAAYgAQyBRAAGIAEMgUQABiABDIFEAAYgARIsR1QhwpY8RtwBngAkAEAmAFboAHSBaoBATm4AQPIAQD4AQGYAg-gArsGwgIEECMYJ8ICBBAAGAPCAg4QABiABBixAxiDARiKBZgDAIgGAZIHBDEzLjKgB_wv&sclient=gws-wiz-serp" target="_blank">
<button class="get-bored-button">GET BORED</button>
</a>
```
```css
.get-bored-button{
    margin-top: 20px;
    background-color: rgba(0, 0, 0, 0.15);
    border-style: none;
    color: rgb(255, 255, 255);
    border-radius: 30px;
    cursor: pointer;
    padding-top: 15px;
    padding-bottom: 15px;
    padding-left: 26px;
    padding-right: 26px;
    font-weight: 600;
    font-size: 15px;
    transition: box-shadow 0.15s;
}

.get-bored-button:hover{
    box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.15);
}
```

5. Set the image using **img** tag and **src** attribute to locate the icon file.
```html
<img class="main-image" src="sources\images\main-image.svg">
```
```css
.main-image{
    height: 350px;
```



### Second Section
The interface
<img src= "sources\readme\section-2.png" alt="section-2">

The nested layout
<img src= "sources\readme\section-2-disect.png" alt="disect">


1. Add **section** tag to create semantic tag
2. Make two horizontally distributed grid contained the desired elements.
    - Set the **display** attribute to grid
    - Set the **grid-template-columns** to 1fr 1fr, to make two equal width grids.
    - Adjust the **margin**, **column-gap** and **column-row** to desired number.

```html
 <section class="text-sect"> 
    <div class="why-bored-explained">
        ...
    </div>
    <div class="vsauce-boredom">
        ...
    </div>
```
```css
.text-sect{
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-top: 170px;
    margin-right: 30px;
    margin-left: 30px;
    column-gap: 20px;
    height: 315px;
}

.why-bored-explained{
    padding-right: 30px;
}
```
2. Set the image using **img** tag and **src** attribute to locate the icon file.
```html
<img class="bored-image" src="sources\images\why-bored.svg">
```
```css
.why-bored-image{
    text-align: right;
}

.bored-image{
    margin-top: 15px;
    width: 66%;
}
```
3. Add **h2** tag to make a semantic second header.
    - Set the **font-size** to adjust the font size of the title.
```html
<h2 class="ssh-left-why-bored">Boredom is good, here's why</h2>
```
```css
.ssh-left-why-bored{
    padding: 0;
    padding-left: 15px;
    margin: 0;
    margin-top: 20px;
    font-size: 30px;
}
```
4. Create unordered list with **ul** tag followed by **li** tag for the items.
    - Set **list-style** to none to clear the bullet.
    - On **.list-style li** set the **margin-top** to adjust the height between the items.
    - On **.list-style li:before** set content to " -", to insert dash before each item.
```html
<ul class="list-style">
    <li>Creativity Booster</li>
    <li>Reflection and Self-Discovery</li>
    <li>Improves Focus and Concentration</li>
    <li>Encourages Mindfulness</li>
    <li>Stress Reduction</li>
</ul>
```
```css
.list-style{
    list-style: none ;
    padding: 0;
    padding-left: 15px;
    margin: 0;
    margin-top: 10px;
    font-size: 15px;
    font-weight: 400;
}

.list-style li{
    margin-top: 5px;
}

.list-style li:before{
    content: "- ";
}
```
5. Set **iframe** tag to attach video from youtube.
    - Add **src** attribute, then insert embed link from any youtube video.
    - Set **allow** to fullscreen, that makes the video can be seen at fullscreen at page.

```html
<iframe class="vsauce-boredom-video" src="https://www.youtube.com/embed/Qwd25JV-jnU?si=73oMtepE2-BSPKla?"allow="fullscreen"></iframe>
```
```css
.vsauce-boredom-video{
    height: 315px;
    width: 560px;
}
```
### Third Section : Data
<img src= "sources\readme\section-3.png" alt="section-3">

1. Add **section** tag to create semantic tag.
2. Add **form** tag indicating a form for user input.
    - Left the **action** attribute blank.
    - Set the **method** attribute to get, that makes the URL querry visible.
3. Create seven row of containers
    - Set **display** to flex for a row that has than one column, that makes easier to arrange the elements.

```html
<section class="data-sect">
        <form action="" method="get">
            <h3 class="data-submit-title">Drop your address and I will pay a visit to your nearby ponds</h3>
            <div class="data-sub-cont">
                <div class="first-row">
                    ...
                </div>
                    
                <div class="second-row">
                    ...
                </div>

                <div class="third-row">
                    ...
                </div>

                <p class="duck-race">Highly suggest to select them all ;)</p>
                <div class="fourth-row">
                     ...
                </div>

                <p class="tip-pizza">How many pizza slices are you willing to invest?</p>
                <div class="fifth-row">
                    ...
                </div>

                <div class="sixth-row">
                    ...
                </div>

                <div class="seventh-row">
                    ...
                </div>
            </div>
        </form>
    
    </section>
```
```css
.data-sect{
    border-width: 1px;
    border-color: rgb(255, 202, 210);
    border-radius: 20px;
    margin-top: 200px;
    margin-right: 30px;
    margin-left: 30px;
    max-width: 980px;
    padding-left: 5%;
    padding-right: 5%;
}

.data-submit-title{
    font-size: 22px;
}

.data-sub-cont .first-row {
    display: flex;
    column-gap: 20px;
    row-gap: 20px;
    margin-top: 20px;
}
.data-sub-cont .second-row {
    display: flex;
    margin-top: 20px;
}
.data-sub-cont .third-row,
.data-sub-cont .fourth-row,
.data-sub-cont .fifth-row {
    display: flex;
    column-gap: 20px;
    row-gap: 20px;
    align-items: center;
    margin-top: 13px;
}
.data-sub-cont .third-row{
    margin-top: 20px;
}

.data-sub-cont .fourth-row,
.data-sub-cont .fifth-row{
    justify-content: left;
}
.data-sub-cont .sixth-row {
    margin-top: 20px;
}
.data-sub-cont .seventh-row {
    display: flex;
    align-items: center;
    margin-top: 20px;
}
```
4. There are 8 kind of forms at this section.
    - Text input.
    - Email input.
    - Select option.
    - Text input (5 digit numbers).
    - Checkbox input.
    - Radio input.
    - Text area
    - Submit

- Text Input
    - **type** attribute to define the type of the input, in this case it is text.
    - **pattern** attribute to specifies the user input.
    - **name** attribute to specifies the name of the element reference.
    - **required** attribute to specifies the element that must be filled before submitting.

```html
<input class="data-postal-code" type="text" pattern="[0-9]{5}" placeholder="Postal Code" name="submit-postalcode" required> 
```
- Email input
        - Email **type** input, it requires the user to fill in the form using email format.

```html
<input class="data-email" type="email" placeholder="duck@something.com" name="submit-email" required> 
```
- Select, Option
        - Set up a dropdown list select menu.
        - **Option** Set up the list items.

```html
<input class="data-city" type="text" placeholder="City" name="submit-city" required> 
    {<select class="data-province" name="submit-province">
        <option value="EastJav">East Java</option>
        <option value="CentJaw">Central Java</option>
        <option value="WestJav">West Java</option>
    </select>}
```

- Text area
    - Setup a textbox for user input.
```html
<textarea class="data-textarea" name="comments" placeholder="Insert kind words here"></textarea>
```
 - Checkbox and Radiobutton input
    - **label** to associate a label(text) to certain elment with the same element value (id).
    - **id** to specify a unique id.
    - **value** to specify the value of an input element.
    - The difference between checkbox and radiobutton is, for checkbox user can select all the items. But for the radiobutton, user can only select one of the items.

```html
Checkbox

<div class="left-option">
    <input class="lcc" type="checkbox" id="mallard" name="submit-duck" value="mallard">
    <label for="mallard"> Mallard Duck</label>
</div>
<div class="middle-option">
    <input class="mcc" type="checkbox" id="pekin" name="submit-duck" value="pekin">
<label for="pekin"> Pekin Duck</label>
</div>
<div class="right-option">
    <input class="rcc" type="checkbox" id="mandarin" name="submit-duck" value="mandarin">
    <label for="mandarin"> Mandarin Duck</label>
</div>
```

```html
Radiobutton

<div class="left-option">
    <input class="lrr" type="radio" id="noslice" name="pizza-slices" value="noslice">
    <label for="noslice">No slice at all?</label>
</div>
<div class="middle-option">
    <input class="mrr" type="radio" id="fewslices" name="pizza-slices" value="fewslices">
    <label for="fewslices"> 1 - 5 slice(s)</label>
</div>
<div class="right-option">
    <input class="rrr" type="radio" id="manyslices" name="pizza-slices" value="manyslices">
    <label for="manyslices"> 5+ slices</label>
</div>
```

- Submit
    - To submit all of the datas that have been input on the form.

```html
<input class="submit-button" type="submit" value="Submit">
```




### Footer
<img src= "sources\readme\footer.png" alt="footer">

they are just texts nothing much really, aside from margin, padding, font-size, etc. just basics styling.
