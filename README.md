# Scroller.js
Create pausable scrolling text with a simple one-liner<br>

## Installation
Install from the command line:
```shell
$ npm install @kezoponk/scroller
```
Install via package.json:
```json
"@kezoponk/scroller": "1.0.7" 
```
Or download Scroller.min.js or AnimatedScroller.min.js from dist/
```html
<script type="text/javascript" src="Scroller.min.js"></script>
```
<br>

## Usage
| Options | Usage |
| --- | --- |
| `direction` | Left or right |
| `speed` | Turtle: 20 - Rabbit: 120 |
| `animation`<br/>&nbsp;**AnimatedScroller** | Animation type, works with cubic-bezier<br>Default: ease-in-out |
| `delay`<br/>&nbsp;**AnimatedScroller** | Delay before starting next animation when last animation is finished |
| `finishAnimationBeforePause`<br/>&nbsp;**AnimatedScroller** | Default: false |

<code>new Scroller <strong>OR</strong> AnimatedScroller('div-containing-buttons', { Options})</code>
### Methods
* pause()<br>
* unpause()<br>
* restore()<br>

<br>

### Example 1 / 3

```html
<div id="scrolldiv" class="scroll-left">
  <button class="scrollbutton">Example</button>
  <button class="scrollbutton">Political</button>
  <button class="scrollbutton">App</button>
  <button class="scrollbutton">Programming</button>
  <button class="scrollbutton">Feminist</button>
  <button class="scrollbutton">Program</button>
  <button class="scrollbutton">School</button>
</div>
```
```javascript
new Scroller('#scrolldiv', { direction: 'left', speed: 10 });
```
- Scroll to left
- Moving 1px every 10ms

<br>
    
### Example 2 / 3

```html
<div id="animated" style="display:flex; flex-direction:column; max-height:100px">
  <a href="/example"><button style="min-height:50px">Example</button></a>
  <a href="/political"><button style="min-height:30px">Political</button></a>
  <a href="/app"><button style="min-height:30px">App</button></a>
  <a href="/programming"><button style="min-height:30px">Programming</button></a>
  <a href="/feminist"><button style="min-height:30px">Feminist</button></a>
  <a href="/program"><button style="min-height:30px">Program</button></a>
  <a href="/school"><button style="min-height:30px">School</button></a>
</div>
```
```javascript
new AnimatedScroller('#animated', { direction: 'right', speed: 100, animation:'linear', delay: 500 });
```
- Scroll to right
- Moving 1px every 100ms
- Div is 50px height
- Ease-in-out animation on each item
- 0.5s delay between each iteration

<br>

### Example 3 / 3

```html
<div class="scroll-right">
  <button onclick="window.location=example.html">Example</button>
  <button onclick="window.location=political.html">Political</button>
  <button onclick="window.location=app.html">App</button>
  <button onclick="window.location=programming.html">Programming</button>
  <button onclick="window.location=feminist.html">Feminist</button>
  <button onclick="window.location=program.html">Program</button>
  <button onclick="window.location=school.html">School</button>
</div>
```
```javascript
new Scroller('.scroll-right', { direction: 'right', speed: 100 });
```
- Scroll to right
- Moving 1px every 100ms
