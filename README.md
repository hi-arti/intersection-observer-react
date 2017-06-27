[![build status](https://secure.travis-ci.org/survivejs/react-component-boilerplate.svg)](http://travis-ci.org/survivejs/react-component-boilerplate) [![bitHound Score](https://www.bithound.io/github/survivejs/react-component-boilerplate/badges/score.svg)](https://www.bithound.io/github/survivejs/react-component-boilerplate) [![Dependency Status](https://david-dm.org/survivejs/react-component-boilerplate.svg)](https://david-dm.org/survivejs/react-component-boilerplate)

# React IntersectionObserver

A simple wrapper around IntersectionObserver API to use it within react apps.


## Basic Usage

`npm install react-intersection-observer`

```js
  import { IntersectionObserver, Observable} from 'react-intersection-observer'
  
  render() {
    return (<IntersectionObserver>
      <Observable
        onEnter={ () => {

        }}
        onLeave={ () => {
          
        }}
      >
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
        quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
        consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
        cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
        proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </Observable>
    </IntersectionObserver>)
  }
  
```


## IntersectionObserver

### Options
Same options as [Intersection_Observer_API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

```
var options = {
  root: document.querySelector('#scrollArea'),
  rootMargin: '0px',
  threshold: 1.0
}
```

#### root
> The element that is used as the viewport for checking visiblity of the target. Defaults to the browser viewport if not specified or if null.

#### rootMargin  
> Margin around the root. Can have values similar to the CSS margin property, e.g. "10px 20px 30px 40px" (top, right, bottom, left). If the root element is specified, the values can be percentages. This set of values serves to grow or shrink each side of theroot element's bounding box before computing intersections. Defaults to all zeros.

#### threshold
> Either a single number or an array of numbers which indicate at what percentage of the target's visibility the observer's callback should be executed. If you only want to detect when visibility passes the 50% mark, you can use a value of 0.5. If you want the callback run every time visibility passes another 25%, you would specify the array [0, 0.25, 0.5, 0.75, 1]. The default is 0 (meaning as soon as even one pixel is visible, the callback will be run). A value of 1.0 means that the threshold isn't considered passed until every pixel is visible.


## Observable


```
 <Observable
    onEnter={ () => {
      // send GA impression
    }}
    onLeave={ () => {
      // Do nothing :D 
    }}
>
```


>  it is both possible and advised to observe multiple elements using the same IntersectionObserver instance by calling observe() multiple times.

Thus  we provided the `<IntersectionObserver>` element, however if an `Observable` is not present within an `IntersectionObserver` context, it will still operate as expected.