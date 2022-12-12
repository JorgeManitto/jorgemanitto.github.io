<template>
<div>
  <div class="item item--0">
    <slot name="img">
        <img width="32" height="32" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1184px-Vue.js_Logo_2.svg.png" alt="">
    </slot>
  
    <span class="text text--1"><slot name="title">Vuejs</slot> </span>
  </div>
</div>
</template>

<style scoped>


.item {
 border-radius: 10px;
 width: 100%;
 height: 100%;
 display: flex;
 flex-direction: column;
 align-items: center;
 justify-content: center;
}

.item:hover {
 transform: scale(0.95);
 transition: all 0.3s;
}

.item svg {
 width: 40px;
 height: 40px;
 margin-bottom: 7px;
}

.item--0 {
 background: #fff;
 border:1px solid #282828;
}
.item--1 {
 background: #c7c7ff;
}

.item--2 {
 background: #ffd8be;
}

.item--3 {
 background: #a9ecbf;
}

.item--4 {
 background: #f3bbe1;
}

.quantity {
 font-size: 25px;
 font-weight: 600;
}

.text {
 font-size: 12px;
 font-family: inherit;
 font-weight: 600;
}

.text--1 {
 color: #000;
}

.text--2 {
 color: rgba(252,161,71,1);
}

.text--3 {
 color: rgba(66,193,110,1);
}

.text--4 {
 color: rgba(220,91,183,1);
}
</style>