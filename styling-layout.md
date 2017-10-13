Mobile Web Expert
====


Basic Website Layout and Styling
----


### DOM access

Given you have the following HTML document.

```
<div class="mdc-card">
  <section class="mdc-card__primary">
    <h1 class="mdc-card__title mdc-card__title--large">Title goes here</h1>
    <h2 class="mdc-card__subtitle">Subtitle here</h2>
  </section>
  <section class="mdc-card__supporting-text">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
    veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
    commodo consequat.
  </section>
  <section class="mdc-card__actions">
    <button class="mdc-button mdc-button--compact mdc-card__action">Action 1</button>
    <button class="mdc-button mdc-button--compact mdc-card__action">Action 2</button>
  </section>
</div>
```

#### How do you select the the card title element with JavaScript?

```
let title = document.querySelector('.mdc-card__title');
```

#### How do you select all of the `<section/>` elements with JavaScript?

```
let sections = document.querySelectorAll('section');
```

#### How do you select the last `<button/>` action element with JavaScript?

```
let lastButton = document.querySelector('.mdc-card__action:last-child')
```

#### What are some common selectors used in `querySelector` and `querySelectorAll`?

- Class selectors such as `.mdc-card` to mach `<div class="mdc-card"></div>`
- ID selectors such as `#card` to mach `<div id="card"></div>`
- Attribute selectors such as `[data-quantity="3"]` to mach `<div data-quantity="3"></div>`

#### APIs

- [Document.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
- [Document.querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
- [Element](https://developer.mozilla.org/en-US/docs/Web/API/element)
- [CSS Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Selectors)


### DOM manipulation

Given you have the following HTML document.

```
<div class="mdc-card">
  <section class="mdc-card__primary">
    <h1 class="mdc-card__title mdc-card__title--large">Title goes here</h1>
    <h2 class="mdc-card__subtitle">Subtitle here</h2>
  </section>
  <section class="mdc-card__supporting-text">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
    veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
    commodo consequat.
  </section>
  <section class="mdc-card__actions">
    <button class="mdc-button mdc-button--compact mdc-card__action">Action 1</button>
    <button class="mdc-button mdc-button--compact mdc-card__action">Action 2</button>
  </section>
</div>
```

#### How do you change the text of the title with JavaScript?

```
document.querySelector('mdc-card__title').innerText = 'Another title';
```

#### How do you add a third `<button />` with JavaScript?

```
let action3 = document.createElement('button');
action3.innerText = 'Action 3';
document.querySelector('.mdc-card__actions').appendChild(action3);
```

#### How do you add classes to the third action `<button />` with JavaScript?

```
let action3 = document.querySelector('.mdc-card__action:last-child');
action3.classList.add('mdc-button', 'mdc-button--compact', 'mdc-button__action');
```

#### What are some other ways of manipulating elements in a document?

- [Node.removeChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)
- [Node.replaceChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)
- [Node.insertBefore()](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)
- [Node.hasChildNodes()](https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes)
- [ParentNode.append()](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/append)

#### APIs

- [Node.innerText](https://developer.mozilla.org/en-US/docs/Web/API/Node/innerText)
- [Document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
- [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
- [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)


### Document declarations and viewport tags

#### What is the base Doctype and tag to define an HTML page with?

```
<!DOCTYPE html>
<html>
  <head>...</head>
  <body>...</body>
</html>
```

#### What is the viewport tag to tell browsers your page is mobile friendly?

```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

`width=device-width` is a way to telling the browser the to set the width of the viewport to the actual width of the current device. `initial-scale=1` says to set the initial zoom to match CSS pixels to viewport pixels.


#### APIs

- [Doctype](https://developer.mozilla.org/en-US/docs/Glossary/Doctype)
- [<html>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
- [Using the viewport meta tag to control layout on mobile browsers](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)
- [Responsive Web Design Basics](https://developers.google.com/web/fundamentals/design-and-ux/responsive/)


### Responsive CSS layout

#### What are some common column counts for mobile, tablet, and desktop grids?

- mobile: 4 columns
- tablet: 8 columns
- desktop: 12 columns

#### What are some common device width breakpoints?

- mobile: width < 480px
- tablet: 480px >= width < 840px
- desktop: 840px >= width < 1600px
- large desktop: 1600px <= width


### CSS media queries

#### How to you write a CSS media query to match a tablet size device?

```
@media (min-width: 480px)  {
  // styles
}
```

#### What are the media types that can be matched against?

- all
- print
- screen
- speech

#### APIs

- [Responsive UI](https://material.io/guidelines/layout/responsive-ui.html)
- [Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [width](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/width)
- [@media](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)


### Multimedia tags

#### How do you embed a video in HTML?

```
<video src="kitten.webm" controls></video>
```

#### How do you provide fallback content if the browser doesn't support `<video />`?

```
<video src="kitten.webm" controls>
  <p>Your browser doesn't support HTML video.</p>
</video>
```

#### How do you support multiple video formats?

```
<video controls>
  <source src="kitten.mp4" type="video/mp4">
  <source src="kitten.webm" type="video/webm">
</video>
```

#### What are some other attributes you can use on a `<video />` tag?

- `width` and `height` to set the dimensions
- `autoplay` to start playing the video without user action
- `loop` to have the video start playing again after finishing
- `muted` to the video without audio
- `poster` to show a an image as the first frame of the video
- `preload` to control buffering of the video

#### How do you embed a audio in HTML?

```
<audio src="kitten.mp3" controls></audio>
```

#### How do you provide fallback content if the browser doesn't support `<audio />`?

```
<audio src="kitten.webm" controls>
  <p>Your browser doesn't support HTML audio.</p>
</audio>
```

#### How do you support multiple audio formats?

```
<audio controls>
  <source src="kitten.mp3" type="audio/mp3">
  <source src="kitten.ogg" type="audio/ogg">
</audio>
```

#### What are some other attributes you can use on a `<audio />` tag?

- `autoplay` to start playing the audio without user action
- `loop` to have the audio start playing again after finishing
- `muted` to start with the audio silenced
- `preload` to control buffering of the audio

#### APIs

- [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
- [<audio>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [<video>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)


### Responsive images

#### How can you embed an image in HTML?

```
<img src="kitten.jpg"
     alt="A cute kitten" />
```

#### How can you change that image embed to load a higher resolution image on a higher resolution display?

```
<img src="kitten.jpg"
     srcset="kitten.jpg 1x,
             cat.jpg 2x"
     alt="A cute kitten" />
```

#### How can you change that image embed to load a larger image on a larger display?

```
<img src="kitten.jpg"
     srcset="kitten.jpg 480w,
             cat.jpg 840w"
     sizes="(max-width: 480px) 100%,
            75%"
     alt="A cute kitten" />
```

#### How can you use a modern image format and fallback to an older format on browsers that don't support it?

```
<picture>
  <source type="image/webp" srcset="kitten.webp">
  <img src="kitten.png" alt="A cute kitten">
</picture>
```

#### APIs

- [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
- [Responsive Images Done Right: A Guide To <picture> And srcset](https://www.smashingmagazine.com/2014/05/responsive-images-done-right-guide-picture-srcset/)
- [Responsive Images Udacity course](https://www.udacity.com/course/responsive-images--ud882)
- [Images](https://developers.google.com/web/fundamentals/design-and-ux/responsive/images)


### Touch events

Touch and mouse events that contain large hit targets on the front end and work
regardless of platform

#### What touch events might a developer encounter?

- `touchstart`
- `touchend`
- `touchmove`
- `touchcancel`

#### How can you listen to a `touchstart` event in JavaScript?

```
document.querySelector('#surface').addEventListener('touchstart', function(event) {
  console.log('touchstart');
});
```

#### If you have a touch surface on a clickable element, how would you keep a click event from firing?

```
document.querySelector('#surface').addEventListener('touchstart', function(event) {
  event.preventDefault();
});
```

#### What's the minimum size a touch target should be?

48px

#### How could you increase the touch target on an element with CSS?

```
<button>Awesome</button>
```

```
button {
  position: relative;
}
button:before {
  position: absolute;
  content: '';
  top: -10px;
  right: -10px;
  left: -10px;
  bottom: -10px;
  cursor: pointer;
}
```

#### APIs

- [Touch events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events)
- [Size Tap Targets Appropriately](https://developers.google.com/speed/docs/insights/SizeTapTargetsAppropriately)
