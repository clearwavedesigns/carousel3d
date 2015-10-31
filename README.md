# Carousel 3D
Responsive 3D carousel plugin.  Loaded with options! ES6 supported.  Strict mode supported. No dependencies.

<p>NOTE: The API only provides one method called "turn". For a small footprint, it's up to the developer to use the turn method in association with any features he/she wants; such as: click navigating, slider navigation, keyboard navigating, swiping, spinning with an ease, etc.</p>

<h2>Use:</h2>
<p>Create as many instances as you need for each of your carousels</p>
<pre>
var c = new Carousel3D({
  box: '.js-carousel1 div', // Required. Container for elements; as selector string
  points: '.js-carousel1 li', // Required. Elements to move around; as selector string
  pointsPercentOf: 0.25, // Optional. Percent of points width, relative to the box's width
  perspective: 0.25, // Optional. Percent relative to the width; as a decimal
  depth: 0.5, // Optional. Viewing depth percent; as a decimal
  float: 'left', // Optional internationalization ordering. "Float" items to the 'left' or 'right'
  animate: 250, // Optional. Animation duration in milleconds; as an int
  fps: 60, // Optional. Frames Per Second; as an int
  opacity: 0.125, // Optional. Opacity percent; as a decimal
  //grayscale: 1, // Optional. Grayscale percent; as a decimal
  //sepia: 1, // Optional. Sepia percent; as a decimal
  blur: 10 // Optional. Blur in pixels; as a number
});
</pre>

<hr/>

<h3>Suggest Dev Snippets:</h3>
<p></p>
<pre>
var dev = {};
dev.degree = 0;
dev.incrementBy = 360 / document.querySelectorAll('.js-carousel1 li').length;

document.querySelector('.js-carousel1 .js-left').addEventListener('click', function() {
  dev.degree -= dev.incrementBy;
  dev.c1.turn(dev.degree);
});
document.querySelector('.js-carousel1 .js-right').addEventListener('click', function() {
  dev.degree += dev.incrementBy;
  dev.c1.turn(dev.degree);
});
document.querySelector('.js-carousel1 input[type="range"]').addEventListener('input', function() {
  dev.c1.turn(parseInt(this.value,10));
});
// You'll want to use the tabindex="-1" hack if you have more than one carousel
window.addEventListener('keydown', function(e) {
  if (e.keyCode === 37) {
    dev.degree -= dev.incrementBy;
    dev.c1.turn(dev.degree);
  } else if (e.keyCode === 39) {
    dev.degree += dev.incrementBy;
    dev.c1.turn(dev.degree);
  }
});
</pre>
