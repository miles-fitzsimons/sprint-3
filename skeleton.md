What happens to the layout when you resize the screen to less than 550 px. How do you think that works?

Upon resizing the screen to less than 550 px the following happens:
The pictures of two iPhones (one on top of the other) turn into a single iPhone and move from the right to the centre of the page. 
The 'Stop coding non-responsive sites. Let users view sites from anywhere' and try skeleton button move from the left of the image to above the image.
The statistics (67% purchae increase etc) move from being inline to being one on top of the other.
The image placeholders in the 'Responsive images' section move from being inline to being one on top of the other.


Inspecting the CSS code reveals a media query that kicks in at a screensize of 550px (reproduced below). There are also other media queries that effect the rendering of the website at min-widths of 750px and 1000px.

The code below queries the screen size, and when it is less than 550px it changes the padding, alignment, heoght and font size of various classes.

/* Bigger than 550 */
@media (min-width: 550px) {
  .section {
    padding: 12rem 0 11rem;
  }
  .hero {
    padding-bottom: 12rem;
    text-align: left;
    height: 165px;
  }
  .phone {
    position: absolute;
    top: -7rem;
    right: 3rem;
    max-height: 362px;
    z-index: 3;
  }
  .phone + .phone {
    top: -6rem;
    display: block;
    max-width: 73.8%;
    right: 0;
    z-index: 2;
    max-height: 338px;
  }
  .hero-heading {
    font-size: 2.4rem;
  }
}



