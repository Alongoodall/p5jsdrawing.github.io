# p5jsdrawing.github.io
Dit is mijn p5js drawing gemaakt in de web editor op virtualbox

var afstand = 200; //je wilt dat de spiraal in het midden begint dus 200 (helft van 400) 
var snelheid = 0.4;
var hoek = 1.0; // Als je de hoek groter maakt zal de spiraal dus ook groter zijn met "krul".
var scalaire = 3; //variabelen opstellen waar je later in de draw funtie gebruik van gaat maken.

function setup() {
  createCanvas(400, 400); //het canvas, je kan de x,y ook vervangen door windowWidth,windowHeight. Je moet de afstand dan ook aanpassen anders zal de spiraal niet altijd in het midden beginnen.
  fill(0);
  background(220);
}

function draw() {
  if (mouseIsPressed) {
    var y = afstand + sin(hoek) * scalaire; //Hier zie je ook dat afstand 200 moet zijn. Zo doe je 200 bij de x en y waarde om de spiraal in het midden te laten beginnen.
  var x = afstand + cos(hoek) * scalaire; //x = cos en y = sin als beide sin zouden zijn krijg je gewoon een lijn, je wil een tegenovergestelde richting.
  randomColor = color(random(255), random(255), random(255));
  fill(randomColor);
  ellipse(x, y, 4, 4);
  hoek += snelheid; //hoek = hoek + snelheid hoe hoger var speed is hoe sneller de balletjes dus ook gaan. De hoek gaat dus telkens met stappen van 0.5 omhoog, de snelheid blijft uiteraard op 0.5..
  scalaire -= snelheid; //scalaire begint bij 3 en gaat met stappen van 0.5 omhoog
  }

}
