# Vera Molnar 
<img src="molnar.jpg" width="600" />

## Start
```js
let tile = 40;
let randomMax=8;
function setup() {
            createCanvas(windowWidth, windowHeight);
        }

function draw() {

             //wie zeichne ich die diagonalen im raster
                //variablen  
                //einfacher loop
                //doppelter loop

            //wie integriere ich den zufall?

            //wie passe ich die liniendicken an?
                //ist das eine lineare progression? map function?
                //oder ist es eine exponentielle progression? https://www.youtube.com/watch?v=zLh0K1PdUbc&list=PL7wAPgl1JVvVJabcmRyEwg8k9rFxCRU9x   https://www.desmos.com/calculator/zukjgk9iry


            //wie kann ich die arbeit weiterentwickeln? z.Bsp. Interaktion integrieren?

            randomSeed(2);
            background(255);
            for (let y = 0; y < height; y = y + tile) {
                for (let x = 0; x < width; x = x + tile) { 
                    let abstand=int(random(-1*randomMax, randomMax));
                    let strichdicke = map(x, 0, width, 1,15);
                    strokeWeight(strichdicke)
                    line(x + tile+abstand, y, x+abstand, y+tile);
                }


                
            }

}

```