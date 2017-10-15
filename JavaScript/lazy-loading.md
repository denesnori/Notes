### Lazy-loading
- loading images on websites asynchronously
  - after the above-the-fold content is loaded
  - conditionally when the images are in the browser's viewport, if you don't scroll down to the image it never loads
- it is common that the scripts wait till the DOM has finished loading before start running
1. simple img lazy load and fade
Initially the ```src``` attribute is replaced by the ```data-src``` attribute.
```
<img data-src='imageLocation' alt='test-image'/>
```

```
img {
  opacity: 1;
  transition: opacity 0.3s;
}
img [data-src] {
  opacity: 0;
}
```
JS adds the ```src``` attribute to each image.
```
[].forEach.call(document.querySelectorAll('img[data-src]'), function(){
    img.setAttribute('src', img.getAttribute('data-src'));
    img.onload = function(){
      img.removeAttribute('data-src');
    }
  })
```


## References:
- (Five techniques to lazy load images)[https://www.sitepoint.com/five-techniques-lazy-load-images-website-performance/]
