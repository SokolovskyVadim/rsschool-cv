# My resume  
  
## About me  
  
Hello my name is **Vadim Sakalouski** and I’m a junior front end developer.  
  
My contacts - *phone: +37544-702-47-05, email: sokolovsky.v.a@gmail.com*.  
  
## My goals  
  
My goal is to be a great developer! I very like what I do and this is important thing. I really like to learn something new, sometimes I can study for 12 hours or searching for the answers to different questions.  

## Skills and experience

I have experience with HTML5, CSS3, JavaScript, jQuery, Bootstrap, Materialize, and little bit with WordPress, PHP.  
  
Check my work's [here](https://github.com/SokolovskyVadim/SokolovskyVadim.github.io).
Check my homework on JS [here](https://repl.it/repls).
  
## Code examples 
  
Some code examples:
  
**HTML**  
  
```
<img class="rot" src="https://cdn.iconscout.com/icon/free/png-256/grinning-face-smile-emoji-happy-37705.png">
<div class="cards">
  <div class="card">
    <h2><a href="#">Title</a></h2>
    <p>Some article description stuff.</p>
  </div>
  <div class="card">
    <h2><a href="#">Title</a></h2>
    <p>Some article description stuff.</p>
  </div>
  <div class="card">
    <h2><a href="#">Title</a></h2>
    <p>Some article description stuff.</p>
  </div>
  <div class="card">
    <h2><a href="#">Title</a></h2>
    <p>Some article description stuff.</p>
  </div>
  <div class="card">
    <h2><a href="#">Title</a></h2>
    <p>Some article description stuff.</p>
  </div>
</div>
```
  
**CSS**  
  
```
img.rot {
  animation: 1s linear 0s normal none infinite running rot;
  -webkit-animation: 1s linear 0s normal none infinite running rot;
  width: 100px;
}
@keyframes rot {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
@-webkit-keyframes rot {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
body {
  margin: 0;
  height: 100vh;
  display: grid;
  place-items: center;
  background: #666;
  overflow: hidden;
}
.cards {
  display: flex;
}
.card {
  background: white;
  border-radius: 1rem;
  padding: 1.5rem;
  box-shadow: 3px 3px 12px 2px rgba(black, 0.6);
  transition: 0.2s;
}
.card:not(:first-child) {
  margin-left: -2rem;
}
.card:not(:last-child):hover,
.card:not(:last-child):focus-within {
  transform: translateY(-1rem);
  ~ .card {
    transform: translateX(2rem);
  }
}
```
  