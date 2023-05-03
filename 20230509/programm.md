# Arrays, Pixels

## Artwork
<img src="Kenneth_Knowlton-scaled.jpg" width="500" />
<br/>
Kenneth C. Knowlton <br/>
http://dada.compart-bremen.de/item/artwork/1267 <br/>
<br/>

## Exercise Work with Images, Arrays and Pixels
```js
//load an image https://p5js.org/reference/#/p5/loadImage
let img = loadImage('assets/laDefense.jpg');

// get color of a region in the image https://p5js.org/reference/#/p5.Image/get
let c = myImage.get(60, 90);
// loop through an fetch the brightness in the upper left corner of the grid  https://p5js.org/reference/#/p5/brightness
let value = brightness(c);

// draw a ellipse or rect (or any element) in the this brightness 
// make the element smaller or bigger according to the brightness
// https://p5js.org/reference/#/p5/map   
// https://p5js.org/reference/#/p5/scale 
// user push, pop, translate to scale
push();
translate(x+rasterbreite/2,y+rasterhoehe/2);
scale(s);
rectMode(CENTER);
rect(0,0,rasterbreite, rasterhoehe);
pop()

// load a text about being a human and display text as element  https://p5js.org/reference/#/p5/loadStrings 

// capture Camera, load image from video stream  https://p5js.org/reference/#/p5/createCapture

```
## Artwork
* Kyle McDonald, Poem Portrait, 2019 https://kylemcdonald.net/ 
* Ryan Alexander, Mycelium, https://www.flickr.com/photos/onecm/sets/72157600033861485/
* Olivia Jack, Selfie Apocalypse https://ojack.xyz/articles/selfie-apocalypse/index.html

## Tutorials 
* Image Processing in p5.js https://idmnyu.github.io/p5.js-image/Filters/vid_filter.html
* Erklärung Pixel Array: https://creative-coding.decontextualize.com/video/
* Work with Text in p5.js https://creative-coding.decontextualize.com/text-and-type/