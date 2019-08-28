# Web App Intro

#### Summary and Objective
For this exercise you will begin with a basic HTML/CSS template for a web application and proceed to customize the content and style to your preference. Through the process you will acquire basic knowledge and intuition about HTML and CSS.

## INSTRUCTIONS

#### 1 Get the Template Code

**HTML**

Copy the following HTML into the `body` of a standard HTML file or directly into the HTML section of Codepen.

```html
<div class="app">
  <div class="nav-bar">
    APP NAME
  </div>
  <div class="main-section">
    <div class="splash">
      <h1>Splash Text Here</h1>
      <h3>Subtext goes here.</h3>
    </div>
    <div class="collection">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item">7</div>
      <div class="item">8</div>
    </div>
  </div>
  <div class="footer">My Footer</div>
</div>
```

**CSS**

Copy the following CSS into a stylesheet file linked in your HTML or directly into the CSS section of Codepen.

```css
body {
  margin: 0;
}

.nav-bar {
  position: sticky;
  top: 0;
  background: black;
  color: white;
  padding: 11px;
  font-size: 22px;
}

.footer {
  position: sticky;
  bottom: 0;
  background: black;
  color: white;
  padding: 11px;
  font-size: 14px;
}

.splash {
  padding: 10px;
  background: lightskyblue;
}

.collection {
  background: lightgray;
  padding: 11px;
}

.item {
  background: lightgoldenrodyellow;
  min-height: 200px;
  margin: 10px;
  padding: 7px;
}
```

You should be able to preview the web page and see the template that looks like the middle image shown at the top of this page.

#### 2 Play Around with the Code a Bit

Now, try editing HTML content and CSS styles to see how it changes the browser view. Some changes won't be evident, others will. Don't worry about breaking anything. Remember, you can always restart with the code above. If you are pretty new to HTML and CSS, try the following changes.

- Change some text in the HTML content, like the app name or splash text.
- Change some colors in the CSS. Stick to common color names for now, like red, green, yellow, etc.
- Change some numbers in the CSS where you see `margin`, `padding`, `width`, `top`, `bottom`.

Ultimately, develop a sense of the components of this template, but you don't have to understand everything completely.

> **The following items don't have to be done in a particular order**

#### 3 Modify the Color Scheme to Your Preference

Now let's make some intentional changes. Experiment with differenct combinations of background colors and text colors. You can use color pallete sites, [like this one](https://coolors.co/browser/best/1), to give you ideas. You'll may notice there are three common ways to define colors in CSS.

- `color: red;` using common names
- `color: #FF0000;` using HEX
- `color: rgb(255,0,0)` using RGB

We won't cover the technical details of HEX and RGB here, but you can still copy them from color codes you find on the web.

#### 4 Change the Font Family of Elements

Coming shortly...

#### 5 Change the 
