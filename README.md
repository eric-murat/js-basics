# js-basics
Javascript - Les bases

## Canvas
- Exemple basique : [https://github.com/eric-murat/js-canvas-01](https://github.com/eric-murat/js-canvas-01)
### Elément Canvas en HTML
Placer cet élément dans le body de index.html :
```js
<canvas width="1000px" height="500px" id="canvas"></canvas>
```

### Récupération du Canvas côté JavaScript
Pour accéder à l'élément Canvas :
```js
var cnv = document.getElementById("canvas");
```

### Elément Contexte
Pour accéder à l'élément Context :
```js
var ctx = cnv.getContext("2d");
```
Il faut ensuite appliquer :
```js
ctx.fillStyle="#FFF";
ctx.strokeWeight = 110;
```

### Détection "mouseIsPressed"
Il faut utiliser une variable globale `mouseIsPressed` et la mettre à jour sur les évènements "mouseDown" et "mouseUp" :
```js
var mouseIsPressed = false;
cnv.addEventListener("mousedown",function() {mouseIsPressed = true;});
cnv.addEventListener("mouseup",function() {mouseIsPressed = false;});
cnv.addEventListener("mousemove",function(e) {
  if (mouseIsPressed) {
    ctx.beginPath();
    ctx.arc(e.clientX, e.clientY, 10, 0, Math.PI * 2, true);
    ctx.stroke();ctx.fill();
  }
});
```

## Tuto JS Grafikart
https://www.youtube.com/watch?v=PIU_2SBSZgw&list=PLjwdMgw5TTLVzD9Jq_WBd1crqDwXRn4cw

## Docs
https://devdocs.io/javascript/
