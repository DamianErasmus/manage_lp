# Frontend Mentor - Manage landing page solution

This is a solution to the [Manage landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/manage-landing-page-SLXqC6P5). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview


### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page
- See all testimonials in a horizontal slider
- Receive an error message when the newsletter sign up `form` is submitted if:
  - The `input` field is empty
  - The email address is not formatted correctly

### Screenshot

![PC Version](./PC_version.png)
![Mobile Version](./mobile_version.png)


### Links

- Solution URL: [https://github.com/DamianErasmus/manage_lp](https://github.com/DamianErasmus/manage_lp)
- Live Site URL: [https://demanagelp.netlify.app/](https://demanagelp.netlify.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Javascript
- Utility class CSS
- [Swiper](https://swiperjs.com/) - For the slider

### What I learned

```html
 <div class="swiper-container"></div>
This in itself doesn't do much, but within it is everything needed to make a swiper using external JS and CSS 
libraries.
```
```css
footer .logial,
footer .update_right {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
}
As you can see the flex direction is a column, usually I would use a grid for this, but in this case I found 
that it would be more effective to use a new learned flex-direction column technique.
```
```js
//Custom Error Message
const form = document.querySelector('footer form');

form.addEventListener("invalid", function (event) {
    event.preventDefault();
}, true);

// Support Safari, iOS Safari, and the Android browser—each of which do not prevent form submissions by default
form.addEventListener("submit", function (event) {
    if (!this.checkValidity()) {
        event.preventDefault();
    }
});

var submitButton = form.querySelector("input[type=submit]");
submitButton.addEventListener("click", function (event) {
    var invalidFields = form.querySelectorAll(":invalid"),
        errorMessages = form.querySelectorAll(".error-message"),
        parent;

    // Remove any existing messages
    for (var i = 0; i < errorMessages.length; i++) {
        errorMessages[i].parentNode.removeChild(errorMessages[i]);
    }

    for (var i = 0; i < invalidFields.length; i++) {
        parent = invalidFields[i].parentNode;
        parent.insertAdjacentHTML("beforeend", "<div class='error-message'> Please enter a valid email </div>");

        invalidFields[i].style.color = "var(--dark-red)";
        invalidFields[i].style.border = "1px solid var(--dark-red)";
    }
});

This took extremely long to figure out, but after a long time of struggling and googling, I was able to 
format the error message for the email input field. It first removes the default browser settings for the 
error message, then applies some functions to give it the style I wanted
```

### Useful resources

- [Swiper API](https://swiperjs.com/swiper-api) - This has everything you need to use the api
- [Progress Telerik](https://www.telerik.com/blogs/building-html5-form-validation-bubble-replacements) - This I used as a guide to customize the form validation


## Author

- Website - [Damian Erasmus](https://damianerasmus.com)
- Frontend Mentor - [@DamianErasmus](https://www.frontendmentor.io/profile/DamianErasmus)
- Github- [Damian Erasmus](https://github.com/DamianErasmus)

