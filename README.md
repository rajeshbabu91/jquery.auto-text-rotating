# jQuery.auto-text-rotating [![README RUS](https://img.shields.io/badge/README-%D0%9F%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D1%8C%20%D0%BD%D0%B0%20%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%BE%D0%BC-brightgreen.svg)](README_RUS.md)
[![GitHub version](https://badge.fury.io/gh/Arttse%2Fjquery.auto-text-rotating.svg)](http://badge.fury.io/gh/Arttse%2Fjquery.auto-text-rotating) [![npm version](https://badge.fury.io/js/jquery.auto-text-rotating.svg)](http://badge.fury.io/js/jquery.auto-text-rotating) [![Bower version](https://badge.fury.io/bo/jquery.auto-text-rotating.svg)](http://badge.fury.io/bo/jquery.auto-text-rotating) [![Travis Ci Build Status](https://api.travis-ci.org/Arttse/jquery.auto-text-rotating.svg)](https://travis-ci.org/Arttse/jquery.auto-text-rotating) [![Codacy Badge](https://www.codacy.com/project/badge/f7bd8ee47c0d476fbbecfcc2e6acb4a4)](https://www.codacy.com/app/arttsesoft/jquery-auto-text-rotating)  [![License MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.txt)

> jQuery plugin to change/rotation of text or html, single or group, automatically with a separator.

## Quick start

### Step one. Installation

#### NPM
```
npm install jquery.auto-text-rotating
```

#### Bower
```
bower install jquery.auto-text-rotating
```

#### Link required files
```html
<!-- Include jQuery library (served from Google) -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<!-- Include jQuery plugin -->
<script src="jquery.auto-text-rotating.min.js"></script>
```

### Step two. Create HTML markup
```html
<div class="element">First|Second|Third</div>
```

### Step three

#### Initialization on one element
```javascript
$('element').atrotating();
```

#### Initialization of the group of elements alternately
```javascript
$('element').atrotating({
    method: 'group'
});
```
When HTML:
```html
<div class="element">First|Fourth</div>
<div class="element">Second|Fifth</div>
<div class="element">Third|Sixth</div>
```

## Settings

The plugin takes the settings as an object.

### type
Type: `string`
Default: `text`
Available:

- `text` — processed just text, cut out all html tags.
- `html` — processed text with html tags.

### method
Type: `string`
Default: `single`
Available:

- `single` — to handle one at a time.
- `group` — to process each element in turn in the group.

### separator
Type: `string`
Default: `|`

The delimiter to separate the text into parts that will change.

### animation
Type: `string`
Default: `fade`

Animation when changing text.

Available:

- `fade` — the effect of the gradual disappearance.
- `scale` — the effect of increasing and decreasing the size of the element.
- `spin` — the effect of increasing or decreasing the size of the element + rotate.

### animationSpeed
Type: `number` or `array`
Default: `300`

The execution speed of animation in milliseconds.

If you specify how `number`, for example — `animationSpeed: 150`, it will be set to the _same value_ for the speed of the animation element in the appearance and disappearance.

If you specify how `array`, for example — `animationSpeed: [300,400]`, it will set a _different value_ for the speed of the animation element in the appearance and disappearance. The first value for the appearance, second to disappearance.

### animationEasing
Type: `string` or `array`
Default: `swing`

Dynamics of execution of the animation. In jQuery is available `linear` and `swing`, but you can use other by connecting the _appropriate extensions (for example, jQuery Easing)_.

If you specify how `string`, for example — `animationEasing: 'linear'`, it will be set to the _same value_ for the dynamics of the animation element in the appearance and disappearance.

If you specify how `array`, for example — `animationEasing: ['swing','linear']`, it will set a different value for the dynamics of the animation element in the appearance and disappearance. The first value for the appearance, second to disappearance.

### animationType
Type: `string`
Default: `full`

Available:
- `full` — animates the selected animation the _appearance and disappearance_.
- `in` — animates the selected animation _only appearance_.
- `out` — animates the selected animation _only disappearance_.

### animationScale
Type: `array`
Default: `[1,0]`

Resize the animation. Only applies to animations `scale` and `spin`. The first value of the array what will be the final size of the element after the gradual appearance of the text. For example, 1 is the standard size, 2 - twice, etc. The second value of the array determines the final size after the gradual disappearance of the item.

### animationRotateDeg
Type: `number`
Default: `720`

The degree of rotation. Applies only to animation `spin`.

### delay
Type: `number`
Default: `2000`

- If you specify how `method: 'single'` — delay between the change of text in milliseconds.
- If you specify how `method: 'group'` — delay between the changing of the text of the elements of the group alternately in milliseconds.

### delayStart
Type: `number`
Default: `2000`

The delay before changing the text.

### delayGroup
Type: `number`
Default: `2000`

- If you specify how `method: 'single'` — doesn't make any sense.
- If you specify how `method: 'group'` — the delay between full bore change the text for all the elements of the group at a time.

### animateOne
Type: `boolean`
Default: `false`

Animate the element, if there are separate parts to change the text.

### trim
Type: `boolean`
Default: `true`

Remove whitespaces at the beginning and at the end of the replaceable parts of the text.

### css
Type: `object`
Default: `undefined`

You can add CSS styles to the element.

```javascript
$('element').atrotating({
    css: {
        "color": "#000",
        "font-size": "20px"
    }
});
```