#_animate.scss
*Just-add-water CSS animation powered by silent SCSS extends*

This is a fork of Dan Eden's wonderful [Animate.css repo](https://github.com/daneden/animate.css). I have modified it to use silent SCSS extends so that all animations are always available, but only those that are used will be printed in a projects compiled css file.

`_animate.scss` is a bunch of cool, fun, and cross-browser animations for you to use in your projects. Great for emphasis, home pages, sliders, and general just-add-water-awesomeness.

##Usage
To use _animate.scss in your website, simply drop the `_animate.scss` file into your project's scss partials directory, import it to your `screen.scss` file, silently the extend `%animated` class to an element, along with any of the animation names. That's it! You've got a CSS animated element. Super!

```scss
//screen.scss
  @import 'partials/_animate.scss'
```

```scss
//_some-partial.scss
.some-element {
  //
  // element styles
  // ...
  @extend %animated;
  @extend %fadeIn;
}
```

You can also detect when an animation ends:

<!--
Before you make changes to this file, you should know that $('#yourElement').one() is *NOT A TYPO*

http://api.jquery.com/one/
-->

```javascript
$('#yourElement').one('webkitAnimationEnd mozAnimationEnd MSAnimationEnd oanimationend animationend', doSomething);
```

**Note:** `jQuery#one` is used when you want to execute the event handler at most *once*. More information [here](http://api.jquery.com/one/).

You can change the duration of your animations, add a delay or change the number of times that it plays:

```scss
.some-element {
  -vendor-animation-duration: 3s;
  -vendor-animation-delay: 2s;
  -vendor-animation-iteration-count: infinite;
}
```

*Note: be sure to replace "vendor" in the CSS with the applicable vendor prefixes (webkit, moz, etc)*

## License
_animate.scss is licensed under the MIT license. (http://opensource.org/licenses/MIT)
