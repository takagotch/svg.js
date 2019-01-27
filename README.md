### svg.js
---
https://github.com/svgdotjs/svg.js

```js
var ns = 'http://www.w3.org/2000/svg'
var div = document.getElementById('drawing')
var svg = document.createElementNS(ns, 'svg')
svg.setAttributeNS(null, 'width', '100%')
svg.setAttributeNS(null, 'height', '100%')
div.appendChild(svg)
var rect = document.createElementNS(ns, 'rect')
rect.setAttributeNS(null, 'width', 100)
rect.setAttributeNS(null, 'height', 100)
rect.setAttributeNS(null, 'fill', '#f06')
svg.appendChild(rect)

var draw = SVG('drawing')
  , rect = draw.rect(100, 100).fill('#f06')
```

```js
var input = document.querySelector('input[type=text]')
var draw = SVG('drawing').viewbox(0, 0, 300, 140)
var text = draw.text(function(add){
  add.tspan( input.value )
})
text
  .path('M10 80 C 40 10, 65 10, 95 80 S 150 150, 180 80')
  .animate(1000, '<>')
  .plot('M10 80 C 40 150, 65 150, 95 80 S 150 10, 180 80')
  .loop(true, true)
input.addEventListener('keyup', updateText(text))
functin updateText(textPath){
  return function(){
    textPath.tspan(this.value)
  }
}

```

```js
var draw = SVG('drawing').size(300, 300)
var rect = draw.rect(100, 100).attr({ fill: '#f06' })

var draw = SVG('drawing').size('100%', '100%')

if(SVG.supported){
  var draw = SVG('drawing')
  var rect = draw.rect(100, 100)
} else {
  alert('SVG not supported')
}

SVG.on(document, 'DOMContentLoaded', function(){
  var draw = SVG('drawing')
})

var draw SVG('drawing')
draw.rect(100, 100).move(100, 50).fill('#f06')


var draw = SVG('drawing')

var nested = draw.nested()
var rect = nested.rect(200, 200)

var group = draw.group()
group.path('M10,20L30,40')
group.add(rect)

var symbol = draw.symbol()
symbol.rect(100, 100).fill('#f09')
var use = draw.use(symbol).move(200, 200)

var defs = draw.defs()
var defs = rect.doc().defs()

var link = draw.link('http://svgdotjs.github.io/')
var rect = link.rect(100, 100)

link.to('http://apple.com')
link.show('replace')
link.target('replace')
link.target('_blank')
rect.linkTo('http://svgdotjs.github.io/')
rect.linkTo(function(link){
  link.to('http://svgdotjs.github.io/').target('_blank')
})
```


