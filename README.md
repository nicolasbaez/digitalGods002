# digitalGods002
Creando estructuras

![digitalGods](https://github.com/nicolasbaez/digitalGods002/blob/master/portada.png)

1. gameDev.htm
```html
<html>
    <script src="p5.js">
        //Descarga: https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.8.0/p5.js
    </script>
    <script src="p5.dom.js">
        //Descarga: https://raw.githubusercontent.com/lmccart/p5.js/master/lib/addons/p5.dom.js
    </script>
    <script src="digitalGods.js">
        //Nuestro juego de video
    </script>
    <body style="margin:0;">
    </body>
</html>
```
2. digitalGods.js
```javascript
//variables
nEdificios=64;
wEdificios=[];
hEdificios=[];
function setup() {
 createCanvas(window.innerWidth,window.innerHeight);
 background(0);
 for(var i=0;i<nEdificios;i++){
   wEdificios[i]=random(width*0.01,width*0.04);
   hEdificios[i]=random(height*0.25,height*0.75);
 }
}
function atardecer(){
    for(var i=height;i>0;i--){
    //rr,gg,bb
    stroke(map(i,height,0,255,0),map(i,height,0,102,0),map(mouseX,0,width,0,255));
    line(0,i,width,i);
  }
}
function draw() {
  atardecer();
  var dx=0;
  noStroke();
  fill(0);
  for(var i=0;i<nEdificios;i++){
    noStroke();
    rect(dx,height-hEdificios[i],wEdificios[i],hEdificios[i]);
    stroke(map(mouseX,0,width,255,0),map(mouseX,0,width,102,0),map(mouseX,0,width,0,255));
    line(dx,height-hEdificios[i],dx+wEdificios[i],height-hEdificios[i])
    dx+=width*0.02;
  }
}
```
