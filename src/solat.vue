<script setup>
import HelloWorld from './components/HelloWorld.vue'
import {ref} from 'vue'

let count = ref(0);
function Increment(){
count.value += 1
}
</script>

<template>
  <div>

  <p style="font-size: 300%;font-weight: bolder;font-family:;">WANTED</p>
  <img id="img" src="https://images.pexels.com/photos/4584411/pexels-photo-4584411.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" style="width:200px;height:300px">
  <P style="font-size: 250%;font-weight: bold;">Dos Santos</P>
  <br>
  <P>{{ count }}</P>
  <button class=" bg-red-200" @click="Increment">Tomato</button>
  
  </div>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
#img{
  animation: mymove 5s infinite;
}
@keyframes mymove {
  50% {transform: rotate(360deg);}
}
</style>
