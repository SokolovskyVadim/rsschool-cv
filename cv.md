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

**JS**  
  
```
'use strict';
function createSVG () {
  // Обертка
  var clockWrap = document.createElement('div');
  var clockWrapWidth = clockWrap.style.width = 300 +'px'; //Устанавливаем размер обертки
  var clockWrapHeight = clockWrap.style.height = 300 +'px'; //Устанавливаем размер обертки
  clockWrap.className = 'clock';

  document.body.appendChild(clockWrap);

  // Сам элемент SVG
  var svgElem = document.createElementNS ('http://www.w3.org/2000/svg', 'svg');
  svgElem.setAttribute('width', clockWrapWidth);
  svgElem.setAttribute('height', clockWrapHeight);
  svgElem.id = 'clock';
  clockWrap.appendChild(svgElem); 

  var clock = document.getElementById('clock');

  // Константы
  const clockWidth = parseInt(clock.getAttribute('width'));
  const clockHeight = parseInt(clock.getAttribute('height'));
  const clockRadius = parseFloat(clockHeight/2);
  const clockCenterX = clockWidth/2;
  const ClockCenterY = clockHeight/2;

  // Создаем циферблат
  var clockCircle = document.createElementNS('http://www.w3.org/2000/svg','circle');
  clockCircle.setAttribute('fill','#fccb66');
  clockCircle.setAttribute('cx',clockCenterX);
  clockCircle.setAttribute('cy',ClockCenterY);
  clockCircle.setAttribute('r',clockRadius);

  clock.appendChild(clockCircle);

  // Создаем цифры на часах
  for(var i = 1; i <= 12; i++) {

    // Создаем обертку для цифр и текста
    var group = document.createElementNS('http://www.w3.org/2000/svg','g');
    group.setAttribute('class','group')
    clock.appendChild(group);
    
    // Создаем часовые деления
    var clockNum = document.createElementNS('http://www.w3.org/2000/svg','circle');
    var angle = parseFloat(i*30)/180*Math.PI;

    clockNum.setAttribute('fill','#46b483');
    clockNum.setAttribute('cx', clockCenterX+(clockRadius-clockWidth/8)*Math.sin(angle)); 
    clockNum.setAttribute('cy', ClockCenterY-(clockRadius-clockWidth/8)*Math.cos(angle)); 
    clockNum.setAttribute('r',clockRadius/8);

    group.appendChild(clockNum);

    var clockNumCenterX = clockNum.getAttribute('cx');
    var clockNumCenterY = clockNum.getAttribute('cy');
    var clockNumRadius = clockNum.getAttribute('r');
    
    // Создаем цифры начасах
    var text = document.createElementNS('http://www.w3.org/2000/svg','text');
    text.setAttribute('x', clockNumCenterX);
    text.setAttribute('y', Number(clockNumCenterY)+clockNumRadius/2);
    text.setAttribute('text-anchor', 'middle');
    text.setAttribute('font-size', clockNumRadius*1.55);

    text.textContent = [i];
    
    group.appendChild(text);
  }

  // Создаем часовую стрелку
  var lineHour = document.createElementNS('http://www.w3.org/2000/svg','line');
  lineHour.setAttribute('stroke','black');
  lineHour.setAttribute('stroke-width', clockRadius/35);
  lineHour.setAttribute('x1',clockCenterX);
  lineHour.setAttribute('y1',ClockCenterY*1.1);
  lineHour.setAttribute('x2',clockCenterX);
  lineHour.setAttribute('y2',ClockCenterY*0.4);

  lineHour.id = 'hand-hour';

  clock.appendChild(lineHour);

  // Создаем минутную стрелку
  var lineMin = document.createElementNS('http://www.w3.org/2000/svg','line');
  lineMin.setAttribute('stroke','black');
  lineMin.setAttribute('stroke-width',clockRadius/50);
  lineMin.setAttribute('x1',clockCenterX);
  lineMin.setAttribute('y1',ClockCenterY*1.1);
  lineMin.setAttribute('x2',clockCenterX);
  lineMin.setAttribute('y2',ClockCenterY*0.3);

  lineMin.id = 'hand-min';

  clock.appendChild(lineMin); 

  // Создаем секундную стрелку
  var lineSec = document.createElementNS('http://www.w3.org/2000/svg','line');
  lineSec.setAttribute('stroke','black');
  lineSec.setAttribute('stroke-width',clockRadius/83.33);
  lineSec.setAttribute('x1',clockCenterX);
  lineSec.setAttribute('y1',ClockCenterY*1.1);
  lineSec.setAttribute('x2',clockCenterX);
  lineSec.setAttribute('y2',ClockCenterY*0.15);

  lineSec.id = 'hand-sec';

  clock.appendChild(lineSec);
  
  // Показываем часы
  var date = document.createElementNS('http://www.w3.org/2000/svg','text');
  date.setAttribute('x', clockCenterX);
  date.setAttribute('y', ClockCenterY-clockRadius/2.75);
  date.setAttribute('text-anchor', 'middle');
  date.setAttribute('font-size', clockRadius/5);
  date.id = 'date';
  
  svgElem.appendChild(date);
  
  // Расставляем стрелки при загрузке часов
  setHands();
}
createSVG();

// Заводим часы
function setHands() {
  var dateTime = new Date();

  var hour = dateTime.getHours();
  var min = dateTime.getMinutes();
  var sec = dateTime.getSeconds();
  var msec = dateTime.getMilliseconds();
  
  var angleHour = (hour%12)/12*360+min/60*30;
  var angleMin = min/60*360;
  var angleSec = sec/60*360;

  var clockCenterX = parseInt(document.getElementById('clock').getAttribute('width'))/2;
  var clockCenterY = parseInt(document.getElementById('clock').getAttribute('height'))/2;

  document.getElementById('date').textContent = dateTime.toLocaleTimeString();
  document.getElementById('hand-hour').setAttribute('transform', 'rotate('+ angleHour +' '+clockCenterX+' '+clockCenterY+')');
  document.getElementById('hand-min').setAttribute('transform', 'rotate('+ angleMin +' '+clockCenterX+' '+clockCenterY+')');
  document.getElementById('hand-sec').setAttribute('transform', 'rotate('+ angleSec +' '+clockCenterX+' '+clockCenterY+')');
}

setInterval(function(){
  setHands();
},1000);  
```  
  
## Education  
  
I studied and study right now in IT-academy.  
i finished courses:  
  
*Basics of web technology* 
  
*Course HTML, CSS, JavaScript, website development training (layout, coding)*  
  
And right now study on:  
  
*JavaScript web application development*

## English level  
  
My english level is something in between intermediate and pre-intermediate. I'm often studied at various courses.