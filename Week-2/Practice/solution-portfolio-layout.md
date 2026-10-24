
# SESSION 2 ASSIGNMENT — DETAILED SOLUTION

## Personal Portfolio — Layout Version

**Course:** Introduction to Web Development  
**Session:** 2  
**Topic:** CSS Box Model, Flexbox, Spacing, and Layout  
**Technologies:** HTML5 and CSS3  
**Difficulty:** Beginner  
**Document Type:** Assignment Solution and Teacher's Guide

---

# 1. INTRODUCTION

## 1.1 Assignment Overview

In Session 2, we learned how to improve the appearance and layout of a webpage using CSS.

We explored the CSS Box Model, margin, padding, borders, border-radius, Flexbox, and responsive design.

In this assignment, we will apply those concepts to improve a personal portfolio website.

Our goal is to transform a basic HTML webpage into a well-organised, visually appealing, and responsive portfolio.

## 1.2 Assignment Requirements

The assignment requires us to:

1. Create a horizontal navigation menu.
2. Add consistent spacing between sections.
3. Use Flexbox in at least two areas.
4. Create three visually distinct skill or interest cards.
5. Improve the layout of the profile image.
6. Keep the HTML and CSS organised.

We will also implement responsive design as an optional bonus.

## 1.3 Expected Result

At the end of the assignment, our website should contain:

- A header displaying our name or personal brand.
- A horizontal navigation menu.
- An introduction section.
- A properly positioned profile image.
- Three skill or interest cards.
- Consistent spacing between elements.
- A footer.
- A layout that adjusts to smaller screens.

---

# 2. PROJECT SETUP

## Step 1: Create the Project Folder

Open Visual Studio Code.

Create a folder named:

`personal-portfolio`

Inside the folder, create the following files and folders:

```text
personal-portfolio/
│
├── index.html
├── style.css
│
└── images/
    └── profile.jpg
```

### Explanation

**index.html**

Contains the HTML elements that define the structure of the webpage.

**style.css**

Contains the CSS rules that control the appearance and layout of the webpage.

**images/**

Stores the images used in the project.

**profile.jpg**

Represents the student's profile picture.

You can replace this image with your own photograph.

Make sure the filename matches the image path used in the HTML.

---

# 3. REQUIREMENT 1: CREATE HORIZONTAL NAVIGATION

## 3.1 Understanding the Requirement

A navigation menu helps visitors move between different parts of a website.

Our portfolio will contain three navigation links:

- Home
- About
- Skills

We want these links to appear horizontally rather than vertically.

We also want the portfolio name to appear on the left and the navigation links on the right.

To achieve this, we will use CSS Flexbox.

## 3.2 HTML Solution

Add the following code inside the `<body>` element:

```html
<header class="site-header">

    <h2 class="logo">Ada.dev</h2>

    <nav class="navigation" aria-label="Main navigation">

        <a href="#home">Home</a>

        <a href="#about">About</a>

        <a href="#skills">Skills</a>

    </nav>

</header>
```

## 3.3 Understanding the HTML

### The `<header>` Element

The `<header>` element represents the introductory area of the webpage.

It commonly contains a logo, website name, or navigation menu.

### The `<h2>` Element

This displays our personal brand:

`Ada.dev`

### The `<nav>` Element

The `<nav>` element identifies a group of navigation links.

### The `<a>` Element

The anchor element creates a clickable link.

For example:

```html
<a href="#skills">Skills</a>
```

This link navigates to the element whose ID is `skills`.

The target section must contain:

```html
<section id="skills">
```

The browser can then navigate to that section when the link is clicked.

## 3.4 CSS Solution

Add the following to `style.css`:

```css
.site-header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    background-color: #172b4d;

    padding: 20px 40px;
}

.logo {
    color: white;
    margin: 0;
}

.navigation {
    display: flex;
    gap: 25px;
}

.navigation a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}
```

## 3.5 Detailed CSS Explanation

### display: flex

```css
display: flex;
```

This turns the header into a Flexbox container.

Its direct child elements become Flexbox items.

In our example, the direct children are:

1. The portfolio name.
2. The navigation menu.

By default, Flexbox arranges these elements horizontally.

### justify-content: space-between

```css
justify-content: space-between;
```

This distributes available space between the Flexbox items.

The first item moves toward the beginning of the row, while the last item moves toward the end.

In our header:

- Ada.dev appears on the left.
- Navigation links appear on the right.

### align-items: center

```css
align-items: center;
```

This aligns the Flexbox items along the cross axis.

Because the default Flexbox direction is `row`, the cross axis is vertical.

Therefore, the logo and navigation are vertically aligned.

### gap: 25px

```css
gap: 25px;
```

This creates 25 pixels of space between the navigation links.

### padding: 20px 40px

```css
padding: 20px 40px;
```

This shorthand means:

- Top padding: 20px
- Bottom padding: 20px
- Left padding: 40px
- Right padding: 40px

Padding creates space inside the header.

### text-decoration: none

```css
text-decoration: none;
```

This removes the default underline from navigation links.

## 3.6 Expected Result

The header should display:

```text
----------------------------------------------------
 Ada.dev                     Home    About    Skills
----------------------------------------------------
```

**Requirement 1 completed.**

---

# 4. REQUIREMENT 2: ADD CONSISTENT SPACING

## 4.1 Understanding the Requirement

A website becomes difficult to read when its elements are too close together.

For example:

- Headings may touch paragraphs.
- Images may appear too close to text.
- Sections may not have enough breathing room.
- Cards may appear crowded.

We can solve these problems using the CSS Box Model.

## 4.2 What Is the CSS Box Model?

Every HTML element is represented as a rectangular box.

The CSS Box Model contains four layers:

1. Content
2. Padding
3. Border
4. Margin

### Content

This is the actual text, image, or other information displayed inside an element.

### Padding

Padding creates space between the content and the border.

### Border

The border surrounds the content and padding.

### Margin

Margin creates space outside the border.

## 4.3 General CSS Solution

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;

    font-family: Arial, sans-serif;

    background-color: #f4f7fc;

    color: #172b4d;
}

section {
    padding: 60px 40px;
}

h1,
h2,
h3 {
    margin-top: 0;
}

p {
    line-height: 1.6;
}
```

## 4.4 Explanation

### Universal Selector

```css
* {
    box-sizing: border-box;
}
```

The `*` selector targets all elements.

`box-sizing: border-box` makes the specified width and height include padding and borders.

For example:

```css
.box {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
}
```

With `border-box`, the total width remains 300px.

Without `border-box`, the total rendered width would be:

300 + 40 + 4 = 344px.

This is because padding and borders would be added to the specified content width.

### Body Margin

```css
body {
    margin: 0;
}
```

Browsers normally apply a default margin to the body.

Setting it to zero removes that space.

### Section Padding

```css
section {
    padding: 60px 40px;
}
```

This adds:

- 60px padding at the top and bottom.
- 40px padding on the left and right.

### Line Height

```css
p {
    line-height: 1.6;
}
```

This increases the space between lines of paragraph text.

The value `1.6` means the line height is 1.6 times the element's font size.

## 4.5 Margin Versus Padding

Consider this example:

```css
.card {
    margin: 20px;
    padding: 30px;
}
```

The margin creates space outside the card.

The padding creates space between the card's content and its border.

### Important Difference

**Margin = External spacing**

**Padding = Internal spacing**

Both properties help improve readability and layout.

**Requirement 2 completed.**

---

# 5. REQUIREMENT 3: USE FLEXBOX IN AT LEAST TWO AREAS

## 5.1 Understanding the Requirement

Flexbox is a CSS layout system that makes it easier to arrange and align elements.

We have already used Flexbox in the header and navigation.

Now we will use it in the introduction section.

Our goal is to position:

- Introduction text on the left.
- Profile image on the right.

## 5.2 HTML Solution

```html
<section class="intro" id="home">

    <div class="intro-text" id="about">

        <h1>Hi, I'm Ada!</h1>

        <p>
            I am an aspiring software engineer
            who enjoys building websites,
            solving problems, and learning
            new technologies.
        </p>

        <a href="#skills" class="btn">
            Explore My Skills
        </a>

    </div>

    <img
        src="images/profile.jpg"
        alt="Portrait of Ada"
        class="profile-image"
    >

</section>
```

## 5.3 CSS Solution

```css
.intro {
    display: flex;

    justify-content: space-between;

    align-items: center;

    gap: 40px;
}

.intro-text {
    flex: 1;
}

.intro-text h1 {
    font-size: 36px;
    margin-bottom: 20px;
}

.intro-text p {
    max-width: 500px;
}
```

## 5.4 Detailed Explanation

### display: flex

This arranges the introduction text and profile image horizontally.

### justify-content: space-between

This distributes available space between the two items.

### align-items: center

This aligns the text container and image vertically within the row.

### gap: 40px

This creates space between the text and image.

### flex: 1

```css
.intro-text {
    flex: 1;
}
```

This allows the introduction text container to grow and occupy available space.

### max-width: 500px

```css
.intro-text p {
    max-width: 500px;
}
```

This prevents the paragraph from becoming excessively wide.

It improves readability on larger screens.

## 5.5 Expected Layout

```text
------------------------------------------------------

 Hi, I'm Ada!                  +------------------+
                               |                  |
 I am an aspiring software     |  Profile Image   |
 engineer who enjoys           |                  |
 building websites.            +------------------+

 [Explore My Skills]

------------------------------------------------------
```

## 5.6 Additional Flexbox Example: Button Styling

```css
.btn {
    display: inline-block;

    background-color: #2563eb;

    color: white;

    padding: 12px 20px;

    margin-top: 15px;

    border-radius: 8px;

    text-decoration: none;

    font-weight: bold;
}
```

The button uses:

- Padding for internal spacing.
- Margin for external spacing.
- Border-radius for rounded corners.
- Background colour for visual emphasis.

**Requirement 3 completed.**

---

# 6. REQUIREMENT 4: CREATE THREE VISUALLY DISTINCT CARDS

## 6.1 Understanding the Requirement

A card is a rectangular container used to display related information.

Cards are commonly used for:

- Skills
- Services
- Products
- Projects
- Testimonials
- Interests

For this assignment, we will create three cards.

Each card will contain:

1. A title.
2. A description.
3. A background colour.
4. Padding.
5. Rounded corners.

The cards will be arranged horizontally using Flexbox.

## 6.2 HTML Solution

```html
<section class="skills" id="skills">

    <h2>My Skills & Interests</h2>

    <p>
        Here are some technologies
        and activities I enjoy.
    </p>

    <div class="cards-container">

        <div class="card html-card">

            <h3>HTML</h3>

            <p>
                I enjoy creating the
                structure of web pages.
            </p>

        </div>

        <div class="card css-card">

            <h3>CSS</h3>

            <p>
                I love designing and
                styling beautiful websites.
            </p>

        </div>

        <div class="card coding-card">

            <h3>Problem Solving</h3>

            <p>
                I enjoy solving problems
                through logical thinking.
            </p>

        </div>

    </div>

</section>
```

## 6.3 CSS Solution

```css
.skills {
    text-align: center;
}

.cards-container {
    display: flex;

    gap: 20px;

    margin-top: 30px;
}

.card {
    flex: 1;

    padding: 30px 20px;

    border-radius: 15px;

    border: 1px solid #ddd;
}

.html-card {
    background-color: #e0edff;
}

.css-card {
    background-color: #f2e8ff;
}

.coding-card {
    background-color: #dcfce7;
}
```

## 6.4 Detailed Explanation

### Shared Card Class

```css
.card {
    flex: 1;
    padding: 30px 20px;
    border-radius: 15px;
    border: 1px solid #ddd;
}
```

All three cards use the same `.card` class.

This ensures that they have consistent:

- Padding
- Border
- Border-radius
- Flexbox sizing

### flex: 1

Each card is allowed to grow and share available space within the Flexbox container.

### Different Background Colours

```css
.html-card {
    background-color: #e0edff;
}
```

This gives the HTML card a light blue background.

```css
.css-card {
    background-color: #f2e8ff;
}
```

This gives the CSS card a light purple background.

```css
.coding-card {
    background-color: #dcfce7;
}
```

This gives the Problem Solving card a light green background.

### Why Use Multiple Classes?

Consider:

```html
<div class="card html-card">
```

This element has two classes:

1. `card`
2. `html-card`

The `.card` class provides the shared styling.

The `.html-card` class provides styling specific to that card.

This approach avoids repeating the same CSS properties for every card.

## 6.5 Expected Layout

```text
------------------------------------------------------

             MY SKILLS & INTERESTS

 +----------------+ +----------------+ +----------------+
 |                | |                | |                |
 |      HTML      | |      CSS       | | Problem Solving|
 |                | |                | |                |
 | Website        | | Website        | | Finding        |
 | structures     | | styling        | | solutions      |
 |                | |                | |                |
 +----------------+ +----------------+ +----------------+

------------------------------------------------------
```

**Requirement 4 completed.**

---

# 7. REQUIREMENT 5: IMPROVE THE PROFILE IMAGE LAYOUT

## 7.1 Understanding the Requirement

The profile image should:

- Have an appropriate size.
- Appear beside the introduction.
- Maintain its proportions.
- Have rounded corners.
- Fit properly within the page layout.

## 7.2 HTML Solution

```html
<img
    src="images/profile.jpg"
    alt="Portrait of Ada"
    class="profile-image"
>
```

## 7.3 CSS Solution

```css
.profile-image {
    width: 220px;

    height: 220px;

    object-fit: cover;

    border-radius: 20px;

    flex-shrink: 0;
}
```

## 7.4 Detailed Explanation

### width

```css
width: 220px;
```

Sets the image width to 220 pixels.

### height

```css
height: 220px;
```

Sets the image height to 220 pixels.

### object-fit: cover

```css
object-fit: cover;
```

This allows the image to fill its assigned dimensions without distortion.

The image maintains its original proportions.

However, some parts may be cropped to fit the available space.

### border-radius

```css
border-radius: 20px;
```

Creates rounded corners.

### flex-shrink: 0

```css
flex-shrink: 0;
```

Prevents Flexbox from shrinking the image when space becomes limited.

## 7.5 Creating a Circular Image

To make the image circular, replace:

```css
border-radius: 20px;
```

With:

```css
border-radius: 50%;
```

Since the image has equal width and height, the result will be circular.

## 7.6 Improving Image Accessibility

The `alt` attribute provides alternative text describing the image.

Example:

```html
alt="Portrait of Ada"
```

This helps screen reader users understand the image.

It can also provide a description if the image fails to load.

**Requirement 5 completed.**

---

# 8. REQUIREMENT 6: ORGANISE HTML AND CSS

## 8.1 Understanding the Requirement

Clean code is easier to:

- Read
- Understand
- Debug
- Maintain
- Update

A well-organised project should separate its HTML structure from its CSS styling.

## 8.2 Use Semantic HTML

Semantic HTML elements describe the meaning of their content.

Examples include:

- `<header>`
- `<nav>`
- `<main>`
- `<section>`
- `<footer>`

### Example

```html
<header>
    <!-- Website header -->
</header>

<main>

    <section>
        <!-- Introduction -->
    </section>

    <section>
        <!-- Skills -->
    </section>

</main>

<footer>
    <!-- Footer information -->
</footer>
```

## 8.3 div Versus section

Use `<section>` when creating a meaningful part of a webpage.

For example:

```html
<section class="skills">
    <h2>My Skills</h2>
</section>
```

Use `<div>` when grouping elements for styling or layout.

For example:

```html
<div class="cards-container">
    <div class="card">HTML</div>
    <div class="card">CSS</div>
</div>
```

## 8.4 Use Meaningful Class Names

Good examples:

```css
.site-header
.navigation
.intro-text
.profile-image
.cards-container
```

Avoid unclear names such as:

```css
.box1
.box2
.abc
.xyz
```

Meaningful class names help other developers understand the purpose of each element.

## 8.5 Use CSS Comments

CSS comments help organise styles into logical sections.

Example:

```css
/* HEADER STYLES */

.site-header {
    display: flex;
}

/* SKILLS SECTION */

.skills {
    text-align: center;
}
```

## 8.6 Use an External Stylesheet

Inside the HTML `<head>`, include:

```html
<link rel="stylesheet" href="style.css">
```

This connects the HTML document to the CSS file.

**Requirement 6 completed.**

---

# 9. BONUS: RESPONSIVE DESIGN WITH MEDIA QUERIES

## 9.1 What Is Responsive Design?

Responsive design allows a website to adjust its layout based on the available screen size.

A responsive website should remain usable on:

- Mobile phones
- Tablets
- Laptops
- Desktop computers

## 9.2 What Is a CSS Media Query?

A media query applies CSS rules only when a specified condition is satisfied.

Example:

```css
@media (max-width: 768px) {
    body {
        background-color: lightblue;
    }
}
```

This means:

If the browser viewport is 768 pixels wide or smaller, change the background colour to light blue.

## 9.3 Responsive Portfolio Solution

Add the following code at the bottom of `style.css`:

```css
@media (max-width: 768px) {

    .site-header {
        flex-direction: column;
        gap: 20px;
        padding: 20px;
    }

    .navigation {
        flex-wrap: wrap;
        justify-content: center;
    }

    section {
        padding: 40px 20px;
    }

    .intro {
        flex-direction: column-reverse;
        text-align: center;
    }

    .intro-text h1 {
        font-size: 28px;
    }

    .profile-image {
        width: 180px;
        height: 180px;
        max-width: 100%;
        border-radius: 50%;
    }

    .cards-container {
        flex-direction: column;
    }

    .card {
        width: 100%;
    }

}
```

## 9.4 Explanation

### flex-direction: column

Changes the Flexbox layout from horizontal to vertical.

### flex-direction: column-reverse

Stacks the elements vertically but reverses their visual order.

In our introduction section, the profile image will appear above the introduction text.

### flex-wrap: wrap

Allows navigation links to move to another line when there is insufficient horizontal space.

### Smaller Padding

```css
section {
    padding: 40px 20px;
}
```

Reduces section padding on smaller screens.

### Vertical Skill Cards

```css
.cards-container {
    flex-direction: column;
}
```

Changes the three cards from a horizontal row to a vertical stack.

---

# 10. COMPLETE FINAL HTML SOLUTION

## File: index.html

Copy the following code into `index.html`.

```html
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Ada | Personal Portfolio</title>

    <link rel="stylesheet" href="style.css">

</head>

<body>

    <!-- HEADER AND NAVIGATION -->

    <header class="site-header">

        <h2 class="logo">Ada.dev</h2>

        <nav class="navigation" aria-label="Main navigation">

            <a href="#home">Home</a>

            <a href="#about">About</a>

            <a href="#skills">Skills</a>

        </nav>

    </header>


    <main>

        <!-- INTRODUCTION SECTION -->

        <section class="intro" id="home">

            <div class="intro-text" id="about">

                <h1>Hi, I'm Ada!</h1>

                <p>
                    I'm an aspiring software engineer
                    passionate about building websites,
                    solving problems, and learning
                    new technologies.
                </p>

                <a href="#skills" class="btn">
                    Explore My Skills
                </a>

            </div>


            <!-- PROFILE IMAGE -->

            <img
                src="images/profile.jpg"
                alt="Portrait of Ada"
                class="profile-image"
            >

        </section>


        <!-- SKILLS SECTION -->

        <section class="skills" id="skills">

            <h2>My Skills & Interests</h2>

            <p>
                Here are some technologies
                and activities I enjoy.
            </p>


            <!-- FLEXBOX CARD CONTAINER -->

            <div class="cards-container">


                <!-- HTML CARD -->

                <div class="card html-card">

                    <h3>HTML</h3>

                    <p>
                        I enjoy creating the
                        structure of web pages.
                    </p>

                </div>


                <!-- CSS CARD -->

                <div class="card css-card">

                    <h3>CSS</h3>

                    <p>
                        I love designing and
                        styling beautiful websites.
                    </p>

                </div>


                <!-- PROBLEM SOLVING CARD -->

                <div class="card coding-card">

                    <h3>Problem Solving</h3>

                    <p>
                        I enjoy solving problems
                        through logical thinking.
                    </p>

                </div>

            </div>

        </section>

    </main>


    <!-- FOOTER -->

    <footer class="site-footer">

        <p>
            &copy; 2026 Ada. All rights reserved.
        </p>

    </footer>

</body>

</html>
```

---

# 11. COMPLETE FINAL CSS SOLUTION

## File: style.css

Copy the following code into `style.css`.

```css
/* =====================================
   1. GENERAL STYLES
===================================== */

* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f4f7fc;
    color: #172b4d;
}

section {
    padding: 60px 40px;
}

h1,
h2,
h3 {
    margin-top: 0;
}

p {
    line-height: 1.6;
}


/* =====================================
   2. HEADER AND NAVIGATION
===================================== */

.site-header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    background-color: #172b4d;
    padding: 20px 40px;
}

.logo {
    color: white;
    margin: 0;
}

.navigation {
    display: flex;
    gap: 25px;
}

.navigation a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.navigation a:hover {
    color: #93c5fd;
}


/* =====================================
   3. INTRODUCTION SECTION
===================================== */

.intro {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 40px;
}

.intro-text {
    flex: 1;
}

.intro-text h1 {
    font-size: 36px;
    margin-bottom: 20px;
}

.intro-text p {
    max-width: 500px;
    color: #475569;
}


/* =====================================
   4. BUTTON
===================================== */

.btn {
    display: inline-block;

    background-color: #2563eb;
    color: white;

    padding: 12px 20px;
    margin-top: 15px;

    border-radius: 8px;

    text-decoration: none;
    font-weight: bold;
}

.btn:hover {
    background-color: #1d4ed8;
}


/* =====================================
   5. PROFILE IMAGE
===================================== */

.profile-image {
    width: 220px;
    height: 220px;

    object-fit: cover;
    border-radius: 20px;

    flex-shrink: 0;
}


/* =====================================
   6. SKILLS SECTION
===================================== */

.skills {
    text-align: center;
}

.skills h2 {
    font-size: 28px;
}

.skills > p {
    color: #64748b;
}


/* =====================================
   7. SKILL CARDS
===================================== */

.cards-container {
    display: flex;
    gap: 20px;
    margin-top: 30px;
}

.card {
    flex: 1;

    padding: 30px 20px;

    border-radius: 15px;
    border: 1px solid #ddd;
}

.card h3 {
    margin-bottom: 15px;
}

.html-card {
    background-color: #e0edff;
}

.css-card {
    background-color: #f2e8ff;
}

.coding-card {
    background-color: #dcfce7;
}


/* =====================================
   8. FOOTER
===================================== */

.site-footer {
    background-color: #172b4d;
    color: white;

    text-align: center;
    padding: 20px;
}

.site-footer p {
    margin: 0;
}


/* =====================================
   9. RESPONSIVE DESIGN
===================================== */

@media (max-width: 768px) {

    .site-header {
        flex-direction: column;
        gap: 20px;
        padding: 20px;
    }

    .navigation {
        flex-wrap: wrap;
        justify-content: center;
    }

    section {
        padding: 40px 20px;
    }

    .intro {
        flex-direction: column-reverse;
        text-align: center;
    }

    .intro-text h1 {
        font-size: 28px;
    }

    .profile-image {
        width: 180px;
        height: 180px;
        max-width: 100%;
        border-radius: 50%;
    }

    .cards-container {
        flex-direction: column;
    }

    .card {
        width: 100%;
    }

}
```

---

# 12. TESTING THE COMPLETED WEBSITE

## Test 1: Navigation

Open the portfolio in a browser.

Check that:

- The website name appears in the header.
- Navigation links appear horizontally on desktop.
- Links have appropriate spacing.
- Clicking Skills navigates to the Skills section.

## Test 2: Spacing

Check that:

- Sections have sufficient padding.
- Text does not touch the edges of the screen.
- Headings and paragraphs are separated.
- Cards have consistent spacing.

## Test 3: Flexbox

Confirm that Flexbox is used in:

1. Header
2. Navigation
3. Introduction
4. Skill cards

## Test 4: Skill Cards

Check that:

- Three cards are visible.
- Each card contains a title.
- Each card contains a description.
- Cards have different background colours.
- Cards have rounded corners.

## Test 5: Profile Image

Confirm that:

- The image loads correctly.
- The image is not stretched.
- The image is positioned neatly.
- The image has rounded corners.

## Test 6: Responsive Design

Resize the browser window.

When the viewport becomes 768px wide or smaller:

- The header should stack vertically.
- The introduction should stack vertically.
- The profile image should appear above the text.
- The skill cards should stack vertically.

---

# 13. COMMON ERRORS AND TROUBLESHOOTING

## Error 1: CSS Is Not Working

### Possible Cause

The stylesheet may not be linked correctly.

### Solution

Confirm that your HTML contains:

```html
<link rel="stylesheet" href="style.css">
```

Also confirm that `index.html` and `style.css` are in the same folder.

## Error 2: Profile Image Is Not Displaying

### Possible Cause

The image path may be incorrect.

### Solution

Check that the image exists at:

```text
images/profile.jpg
```

The filename must match exactly.

For example, `profile.JPG` and `profile.jpg` may be treated as different filenames on some systems.

## Error 3: Flexbox Is Not Working

### Possible Cause

`display: flex` may have been applied to the wrong element.

### Solution

Apply Flexbox to the parent container.

Example:

```css
.cards-container {
    display: flex;
}
```

Flexbox affects the direct children of the container.

## Error 4: Cards Are Too Close Together

### Solution

Increase the gap:

```css
.cards-container {
    gap: 30px;
}
```

## Error 5: Cards Do Not Stack on Mobile

### Possible Cause

The media query may be missing or incorrectly written.

### Solution

Check:

```css
@media (max-width: 768px) {
    .cards-container {
        flex-direction: column;
    }
}
```

Ensure that this code appears after the default card styles.

---

# 14. ASSIGNMENT ASSESSMENT RUBRIC

| Assessment Area | Maximum Marks |
|---|---:|
| Horizontal navigation | 15 |
| Spacing and CSS Box Model | 15 |
| Correct use of Flexbox | 20 |
| Three visually distinct cards | 20 |
| Profile image layout | 10 |
| HTML and CSS organisation | 10 |
| Overall appearance and usability | 10 |
| **Total** | **100** |

## Grading Guidance

### Excellent: 90–100%

All requirements are implemented correctly.

The website is organised, visually consistent, and functional.

The student can explain the CSS properties used.

### Very Good: 80–89%

Most requirements are implemented correctly.

There may be minor styling or layout issues.

### Good: 70–79%

The website meets most requirements but needs improvements in spacing, alignment, or organisation.

### Needs Improvement: Below 70%

Several requirements are incomplete or incorrectly implemented.

The student requires additional practice with the CSS Box Model and Flexbox.

---

# 15. TEACHER'S KNOWLEDGE CHECK

Ask the student the following questions after reviewing the completed project.

### Question 1

Why did we use `display: flex` in the header?

**Expected Answer:**

To arrange the website name and navigation menu horizontally.

### Question 2

What does `justify-content: space-between` do?

**Expected Answer:**

It distributes available space between Flexbox items, placing the first and last items toward opposite ends of the main axis.

### Question 3

What is the difference between margin and padding?

**Expected Answer:**

Margin creates space outside an element's border, while padding creates space inside the border.

### Question 4

Why did we use `object-fit: cover` on the profile image?

**Expected Answer:**

To make the image fill its assigned dimensions while maintaining its proportions, even if some cropping is necessary.

### Question 5

What does `border-radius: 50%` do to a square image?

**Expected Answer:**

It makes the image appear circular.

### Question 6

Why did we give all three cards the class `card`?

**Expected Answer:**

To apply common styling to all the cards without repeating the same CSS rules.

### Question 7

What is the purpose of a media query?

**Expected Answer:**

To apply CSS styles when specific conditions, such as viewport width, are met.

### Question 8

What is the difference between `<div>` and `<section>`?

**Expected Answer:**

`<div>` is a generic container used for grouping elements.

`<section>` represents a meaningful, thematic section of a webpage.

### Question 9

What does `flex-direction: column` do?

**Expected Answer:**

It arranges Flexbox items vertically instead of horizontally.

### Question 10

Why should HTML and CSS be stored in separate files?

**Expected Answer:**

To keep the project organised, readable, reusable, and easier to maintain.

---

# 16. FINAL SUBMISSION CHECKLIST

Before submitting the assignment, confirm the following:

- [ ] The project contains `index.html`.
- [ ] The project contains `style.css`.
- [ ] The profile image loads correctly.
- [ ] Navigation links appear horizontally on desktop.
- [ ] Navigation links work correctly.
- [ ] The introduction and profile image are aligned.
- [ ] Flexbox is used in at least two areas.
- [ ] Three skill cards are present.
- [ ] Cards have different background colours.
- [ ] Cards have consistent padding.
- [ ] Cards have rounded corners.
- [ ] Sections have appropriate spacing.
- [ ] HTML uses meaningful elements.
- [ ] CSS is properly organised.
- [ ] The website works on smaller screens.
- [ ] A screenshot of the completed website has been captured.

---

# 17. EXPECTED LEARNING OUTCOMES

By completing this assignment, the student should be able to:

1. Explain the CSS Box Model.
2. Distinguish between margin and padding.
3. Create a horizontal navigation menu.
4. Use Flexbox to arrange webpage elements.
5. Apply `justify-content` and `align-items`.
6. Create and style reusable cards.
7. Control image dimensions and appearance.
8. Use borders and rounded corners.
9. Organise HTML and CSS files.
10. Apply basic responsive design using media queries.

---

# 18. CONCLUSION

This assignment demonstrates how HTML and CSS work together to create a structured and visually appealing website.

HTML defines the content and meaning of the webpage.

CSS controls the presentation, spacing, colours, and layout.

Flexbox makes it easier to arrange elements horizontally or vertically.

The CSS Box Model helps us control the spacing around and inside elements.

Media queries allow the website to adapt to different screen sizes.

By successfully completing this assignment, the student has developed the foundational layout skills needed to build more advanced websites.

**Final Deliverable:** Personal Portfolio — Layout Version

**End of Session 2 Assignment Solution**
