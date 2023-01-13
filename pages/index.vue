<template>
  <div>
    <div v-for="product in products" :key="product.id" class="grid">
      <div class="image"><img class="skor-img" :src="product.img" /></div>
      <div class="beskrivning">
        <strong class="text">Beskrivning</strong><br /><br />
        <p class="text2">{{ product.beskrivning }}</p>
      </div>
      <div class="pris">
        Köp här<button @click="count++">{{ product.pris }} {{ count }}</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import p from '../data/products.json'
import { ref } from 'vue'

const props = defineProps(['count'])
let products = ref(p)
const count = ref(0)

defineProps: ({
  count: Number,
})
</script>
<style scoped>
img {
  width: 7vw;
  border-radius: 50%;
  margin-top: 2vw;
  margin-left: 2vw;
  transition-duration: 0.5s;
}
img:hover {
  transform: rotate(360deg);
}
.grid {
  display: grid;
  grid-template-columns: auto auto auto;
  gap: 0.5vw;
  margin-top: 1vw;
}
.image {
  position: relative;
  grid-column: 1 / span 2;
  grid-row: 1 / 3;
  width: 50vw;
  height: 30.5vw;
  margin-left: 0.7vw;
  background-color: rgba(255, 255, 255, 0.708);
  border-radius: 0.8vw;
}
.beskrivning {
  grid-column: 3;
  grid-row: 2;
  width: 26vw;
  height: 20vw;
  padding: 1vw;
  background-color: rgba(255, 255, 255, 0.708);
  border-radius: 0.8vw;
  padding-bottom: 2vw;
  margin-right: 0.5vw;
}
.pris {
  width: 26vw;
  height: 5vw;
  padding: 1vw;
  background-color: rgba(255, 255, 255, 0.708);
  border-radius: 0.8vw;
}
button {
  width: 8vw;
  border-radius: 0.7vw;
  border: none;
  padding: 0.5vw;
  background-color: orangered;
  float: right;
  margin-top: 3vw;
  margin-right: 10vw;
  cursor: pointer;
  font-weight: bold;
}
button:hover {
  background-color: rgb(241, 168, 141);
}
button:active {
  transform: scale(0.9);
}
.skor-img {
  position: absolute;
  width: 25vw;
  margin-left: 10vw;
}
.text {
  font-size: 2vw;
}
.text2 {
  font-size: 1vw;
}
@media screen and (max-width: 768px) {
  .hidden {
    display: none;
  }
  .grid {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .image {
    margin-top: 2vw;
    position: static;
    width: 78vw;
    margin-right: 1vw;
  }
  .skor-img {
    margin-left: 25vw;
  }
  .beskrivning {
    display: flex;
    width: 76vw;
    flex-direction: column;
    margin: 1vw;
    height: 80vw;
  }
  .pris {
    position: relative;
    display: flex;
    width: 76.5vw;
    flex-direction: column;
    padding-bottom: 7.5vw;
    margin: 0.6vw;
    margin-bottom: 1vw;
    text-align: center;
    font-size: 3vw;
  }
  button {
    position: absolute;
    width: 76.5vw;
    height: 7vw;
    margin-right: 0.5vw;
    margin-top: 4vw;
  }
  .text {
    font-size: 2.5vw;
  }
  .text2 {
    font-size: 2.5vw;
  }
}
</style>
