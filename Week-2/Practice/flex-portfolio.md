
# Guided Practical: Create a Portfolio Layout Using CSS Flexbox

**Duration:** 25 Minutes  
**Level:** Beginner  
**Technologies:** HTML5 and CSS3

## Learning Objectives

By the end of this practical, you should be able to:

1. Arrange navigation links horizontally using Flexbox.
2. Create a header containing a name and navigation menu.
3. Position an image beside an introduction.
4. Create three skill or interest cards.
5. Add spacing between sections using CSS.
6. Apply margins, padding, borders, and border-radius.

---

## Project Overview

You will build a simple personal portfolio website containing:

- A header with your name and navigation links.
- An introduction section with a short biography.
- A profile picture positioned beside your introduction.
- Three cards displaying your skills or interests.
- Appropriate spacing, colours, and rounded corners.

## Step 1: Set Up Your Project

Create a new folder called:

`portfolio-practical`

Inside the folder, create these files:

```text
portfolio-practical/
├── index.html
├── style.css
└── profile.jpg
```

**Note:** Use any appropriate profile image and rename it `profile.jpg`.

---

## Step 2: Create the HTML Structure

Open `index.html` and add the following:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Header -->
    <header>
        <h2>Ada.dev</h2>

        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
        </nav>
    </header>

    <!-- Introduction -->
    <main>
        <section class="intro" id="home">

            <div class="intro-text" id="about">
                <h1>Hi, I'm Ada!</h1>

                <p>
                    I'm an aspiring software engineer
                    who loves building websites
                    and learning new technologies.
                </p>

                <a href="#skills" class="btn">
                    About Me
                </a>
            </div>

            <img
                src="profile.jpg"
                alt="My profile photo"
                class="profile-image"
            >

        </section>

        <!-- Skills -->
        <section class="skills" id="skills">

            <h2>My Skills & Interests</h2>

            <div class="cards">

                <div class="card">
                    <h3>HTML</h3>
                    <p>Building website structures.</p>
                </div>

                <div class="card">
                    <h3>CSS</h3>
                    <p>Styling beautiful websites.</p>
                </div>

                <div class="card">
                    <h3>Coding</h3>
                    <p>Solving problems with code.</p>
                </div>

            </div>

        </section>
    </main>

</body>
</html>
```

---

## Step 3: Style the Website Using CSS

Open `style.css` and add the following code.

### 3.1 General Styling

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f4f7fb;
    color: #1f2937;
}
```

**Explanation:**

- `box-sizing: border-box` includes padding and borders in an element's specified width.
- `margin: 0` removes the browser's default body margin.
- `font-family` controls the font.
- `background-color` sets the page background.
- `color` sets the default text colour.

### 3.2 Header and Navigation

```css
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 40px;
    background-color: #152b4b;
    color: white;
}

nav {
    display: flex;
    gap: 20px;
}

nav a {
    color: white;
    text-decoration: none;
}
```

**Explanation:**

- `display: flex` arranges child elements in a row by default.
- `justify-content: space-between` places the name and navigation at opposite ends.
- `align-items: center` vertically aligns the items in the row.
- `gap: 20px` creates spacing between navigation links.
- `padding` creates space inside the header.

### 3.3 Introduction Section

```css
.intro {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 30px;
    padding: 60px 40px;
}

.intro-text {
    flex: 1;
}

.profile-image {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 20px;
}
```

**Explanation:**

- Flexbox positions the introduction and image side by side.
- `gap` separates the text from the image.
- `flex: 1` allows the text section to use available space.
- `object-fit: cover` prevents the image from stretching.
- `border-radius` creates rounded corners.

### 3.4 Style the Button

```css
.btn {
    display: inline-block;
    background-color: #2563eb;
    color: white;
    padding: 12px 20px;
    margin-top: 15px;
    border-radius: 8px;
    text-decoration: none;
}
```

**Explanation:**

- `padding` creates space inside the button.
- `margin-top` creates space above it.
- `border-radius` rounds the corners.
- `text-decoration: none` removes the link underline.

### 3.5 Skills and Interest Cards

```css
.skills {
    padding: 40px;
    text-align: center;
}

.cards {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 25px;
}

.card {
    flex: 1;
    background-color: white;
    padding: 25px;
    border-radius: 12px;
    border: 1px solid #ddd;
}
```

**Explanation:**

- `display: flex` arranges the cards horizontally.
- `gap` creates spacing between cards.
- `flex: 1` allows the cards to share available space.
- `padding` creates space inside each card.
- `border` creates a visible boundary.
- `border-radius` rounds the corners.

### 3.6 Responsive Design

Add this code at the bottom of `style.css`:

```css
@media (max-width: 600px) {
    header,
    .intro {
        flex-direction: column;
        text-align: center;
    }

    .cards {
        flex-direction: column;
    }
}
```

**Explanation:**

When the screen width is 600px or smaller, the header, introduction, and skill cards will stack vertically.

---

## Step 4: Test Your Website

1. Save `index.html` and `style.css`.
2. Open `index.html` in your browser.
3. Confirm that the header and navigation display correctly.
4. Check that the profile image appears beside the introduction.
5. Verify that all three skill cards appear horizontally on a wide screen.
6. Resize the browser window to observe the responsive layout.

---

## Step 5: Student Challenges

Complete the following tasks independently.

- [ ] Change the header background colour.
- [ ] Increase the spacing between navigation links.
- [ ] Make the profile picture circular using `border-radius`.
- [ ] Change the skill cards to have rounded corners of `25px`.
- [ ] Add a fourth skill card.
- [ ] Change the introduction layout from horizontal to vertical.

**Bonus Challenge:**

Add a footer containing your name and the current year.

---

## Step 6: Knowledge Check

Answer the following questions:

1. What is the purpose of `display: flex`?
2. What is the difference between `justify-content` and `align-items`?
3. What happens when you use `flex-direction: column`?
4. What is the difference between margin and padding?
5. Which CSS property rounds the corners of an element?
6. What does `gap: 20px` do inside a Flexbox container?
7. Why is `box-sizing: border-box` useful?

---

## Suggested Time Allocation

| Duration | Activity |
|---|---|
| 0–5 minutes | Create the HTML structure |
| 5–10 minutes | Style the header and navigation |
| 10–15 minutes | Build the introduction section |
| 15–20 minutes | Create the three skill cards |
| 20–25 minutes | Test the layout and complete challenges |

---

## Expected Learning Outcome

By completing this exercise, you should understand how to use CSS Flexbox to build a basic portfolio layout.

You should also be able to explain the differences between:

- Margin and padding
- Border and border-radius
- `justify-content` and `align-items`
- Row and column layouts

**Submission:** Submit your completed `index.html`, `style.css`, and a screenshot of your portfolio website.

**End of Practical Exercise 2**
