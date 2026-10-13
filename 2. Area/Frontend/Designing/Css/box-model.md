---
tags:
  - theory
  - css
---

## By default koi bhi div mai , padding , border , margin uske base height / width pe add hote hai ... but box model mai ==height fix hoti hai base height pe and baaki sb adjust hota hai acc==


### generally we use border-box only .. isliye universal selector mai hi border-box rkh dete hai 



```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="box1">Box 1</div>
    <div class="box2">Box 2</div>
  </body>
</html>
```

```css
.box1 {
  /* by default box-sizing : border-box */
  height: 100px;
  width: 100px;
  padding: 20px;
  border: 10px solid red;
}
.box2 {
  box-sizing: border-box;
  height: 100px;
  width: 100px;
  padding: 20px;
  border: 10px solid red;
}
```




![[css box model | 700]]
