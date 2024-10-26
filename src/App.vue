<script setup>
import {onMounted, ref}from 'vue';
import PocketBase from 'pocketbase';

const pb = new PocketBase('http://127.0.0.1:8090');
const name = ref ("");
const data = ref ([])

async function submit(){
 
    const record ={
    title: name.value,
    description:""
    };
    await pb.collection('workshop').create(record);
    data.value.push(record);
}

onMounted(async()=>{
    const result=await pb.collection("workshop").getFullList();
    data.value = result;
})
</script>

<template>
    
    <form>
        <input v-model="name" class="bg-pink-900 text-black px-4 py-1 rounded-lg mx-3 my-3"/>
        <button @click="submit" class="bg-pink-900 text-white px-5 py-2 rounded-lg mx-3 my-3 transition-300 hover:bg">add</button>
    </form>
    

    <ul>
    <li v-for= "item in data">
        {{ item.title }}
    </li>
</ul> 
</template>
