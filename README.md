# WCAG 2.1 Accessible Carousel
The following Carousel can be used as a WCAG Accessible alternative in any website or web application. It is portable, easy to set up and easy to configure.

## Author
Alan Espinet
- [Personal Website](https://alanespinet.com/)
- [LinkedIn Profile](https://www.linkedin.com/in/alan-espinet/)

## Important Notes
- This Carousel handles **ONE** slide at a time, like _Bootstrap's Carousel_.
- This Carousel **always loops**.
- For accessibility reasons, this Carousel **does NOT auto-animates**... (yet).

## Dependencies
- jQuery

## Use
- Import **carousel.min.js** and **carousel.min.css** into your project.
- Make sure **jQuery** is imported BEFORE **carousel.min.js**.
- Create your HTML for the carousel:

```
<div class="acc_carousel">
  <div class="element">
    ... element content here
  </div>

  <div class="element">
    ... element content here
  </div>

  ... more elements here
</div>
```

- In your main **.js** file, create the carousel calling **createCarousel**:

```
$('.acc_carousel').createCarousel();
```

- For creating more than one carousel, use ids or extra classes in the main div **acc_carousel** and call **createCarousel** for each one of them.

## Configure
The function call **createCarousel** receives an optional object with four (4) optional properties. All of these properties have working default values:

- **prevHtml**: HTML Content for the _Prev_ (previous element) button.
- **nextHtml**: HTML Content for the _Next_ (next element) button.
- **wcagDescription**: Simple text used by the **aria-label** attribute of the carousel. This property _forces a change_. Keep in mind that **aria-label** already has a CORRECT value based in this property's default. Use this property wisely.
- **showDots**: Shows the dots panel at the bottom of the carousel. This property's default value is **false**.

### Tips
- Do NOT use ```<a>``` tags for **prevHtml** and **nextHtml**. These properties handle the content for already existing ```<a>``` tags.
- The default content for **wcagDescription** is dynamic, based in the amount of elements the carousel has. That is the very desired value for a carousel's **aria-label**
- The **Dots Panel** shown by **showDots** is NOT reachable by Screen Readers. Individual dots, contrary to non-accessible carousels, are NOT clickable or focusable. This Panel only serves for decoration purposes.

## Configuration Example
The next example uses the optional argument for **createCarousel** in order to configure some aspects of one specific carousel. For this example, **FontAwesome** is considered imported into the project. Besides, a second class is used to target ONLY this carousel:

```
HTML:
------------------------
<div class="acc_carousel some-special-carousel">
  <div class="element">
    ... element content here
  </div>

  <div class="element">
    ... element content here
  </div>

  <div class="element">
    ... element content here
  </div>
</div>

...

JS:
------------------------
$('.acc_carousel.some-special-carousel').createCarousel({
  prevHtml: '<i class="fa fa-chevron-left" aria-hidden="true"></i>',
  nextHtml: '<i class="fa fa-chevron-right" aria-hidden="true"></i>',
  showDots: true
);
```

## Final Notes:
- A very basic set of CSS has been provided. Like any other Carousel, a personalized CSS will be needed for matching every single expected result.
- This Carousel has been tested successfully in Google Chrome, Safari, Mozilla Firefox, Edge and IE 11. It was not tested in Opera or IE 10- versions. For these last ones, its unlikely to work properly, due to the used CSS.
