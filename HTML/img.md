## img tag

- complete prop
```
var loaded = document.getElementById('myImg').complete;
```

 ```img.complete```
- false while loading
- true after the img has finished loading

```
var img = new Image();
img.src =`link to my fancy img`;
img.onload = () => {
  //todo sg
}
```

Create any DOM node: ```document.createElement('div')```


How to check whether the background img has loaded:
```
var bgImg = new Image();
bgImg.onload = function(){
  myDiv.style.backgroundImage = `url(${bgImg.src})`
}
bgImg.src = imageLocation;
```

- does ```display:'none';``` prevent sthe img from loading?
 -Depends: browser, img vs backgroundImg
 - if it is a background image and has display: none it won't load.
