# `@keyframe` example
## Rainbow Heart

```HTML
<style>

#rainbow {
  animation-name: rainbow;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}
@keyframes rainbow {
  16%{
    background-color: red;
  }
  32%{
    background-color: orange;
  }
  48%{
    background-color: yellow;
  }
  64%{
    background-color: green;
  }
  80%{
    background-color: blue;
    }
  96%{
    background-color: purple;
  }
}
.heart {
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: black;
  height: 50px;
  width: 50px;
  transform: rotate(-45deg);
  animation-name: rainbow;
}
.heart:before {
  content: "";
  background-color: black;
  border-radius: 50%;
  position: absolute;
  top: -25px;
  left: 0px;
  width: 50px;
  height: 50px;
  animation-name: rainbow;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}
.heart:after {
  content: "";
  background-color: black;
  border-radius: 50%;
  position: absolute;
  top: 0px;
  left: 25px;
  width: 50px;
  height: 50px;
  animation-name: rainbow;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}
</style>

<div id="rainbow" class="heart">
```
