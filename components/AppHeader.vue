<template>
  <div>
    <div class="corner">
      <picture>
        <img src="~assets/litestörre.jpg" />
      </picture>
      <div>
        <font-awesome-icon id="cart" :icon="['fas', 'cart-shopping']" />
        <parent><div class="count">{{ count }}</div></parent>
      </div>
    </div>
    <div>
      <font-awesome-icon class="height" id="bar" :icon="['fas', 'bars']" />
    </div>
    <div>
      <ul class="menu hidden" id="menu">
        <li>Home</li>
        <li>About</li>
        <li>Cashout</li>
      </ul>
    </div>
  </div>
</template>
<script setup>
import { parent } from '../pages/index.vue'
</script>
<style scoped>
img {
  width: 7vw;
  border-radius: 50%;
  margin-top: 2vw;
  margin-left: 2vw;
  transition-duration: 0.5s;
  justify-content: left;
}
img:hover {
  transform: rotate(360deg);
}
ul {
  display: block;
}
.menu {
  display: flex;
  justify-content: space-around;
}
.fa-bars {
  display: none;
  cursor: pointer;
}
#cart {
  position: absolute;
  font-size: 2vw;
  margin-top: 5vw;
  margin-right: 1vw;
  width: 4vw;
  cursor: pointer;
  color: black;
}
#cart:active {
  transform: scale(0.9);
}
.count {
  position: relative;
  background-color: orangered;
  width: 1vw;
  height: 1vw;
  border-radius: 50%;
  text-align: center;
  padding-top: 0.2vw;
  padding-right: 0.1vw;
  padding-left: 0.1vw;
  font-weight: bold;
  cursor: pointer;
  margin-top: 6vw;
  margin-left: 2vw;
  opacity: 0.8;
}

.corner {
  display: flex;
  flex-wrap: wrap;
  gap: 63vw;
}
.height {
  display: none;
}
li {
  text-align: center;
  list-style: none;
  padding: 0.8vw;
  cursor: pointer;
}
li:hover {
  background-color: orangered;
  border-radius: 15px;
  transform: scale(1.2);
  box-shadow: 1px 1px 1px 1px rgba(244, 172, 148, 0.776);
}
li:active {
  transform: scale(0.98);
}
.change {
  display: absolute;
  float: right;
  border-radius: 15px;
  color: black;
  margin-left: 10vw;
  cursor: pointer;
  padding: 0.8vw;
}
.change:hover {
  font-weight: bold;
  background-color: grey;
  border-radius: 1.5vw;
}
@media screen and (max-width: 768px) {
  .height {
    height: 6vw;
    display: flex;
    justify-content: flex-end;
    width: 100%;
  }
  ul {
    display: flex;
    flex-direction: column;
    padding: 0vw;
    width: 100%;
  }
  li {
    background-color: grey;
    border-radius: 0px;
    height: 6vw;
    padding-top: 2vw;
  }
  li:hover {
    background-color: orangered;
    border-radius: 0px;
    transform: scale(1);
    box-shadow: 0px 0px 0px 0px rgb(249, 248, 248);
  }
  li:active {
    transform: scale(0.98);
  }
  .fa-bars {
    display: block;
    width: 5vw;
    height: 5vw;
    color: black;
    float: right;
    margin-top: 3vw;
    margin-bottom: 5vw;
    padding-right: 1.5vw;
  }
  .fa-bars:hover {
    color: orangered;
  }
  .fa-bars:active {
    transform: scale(1.15);
  }
}
</style>
