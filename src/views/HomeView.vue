<template>
  <div class="home">
    <h1>home</h1> 
    <h2>Refs</h2> 
     <p>{{ ninjaOne.name }} - {{ ninjaOne.age }} - {{ nameOne }}</p>
     <button @click="updateNinjaOne">Click me</button>
    <h2>Reactive</h2> 
     <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }} - {{ nameTwo }}</p>
     <button @click="updateNinjaTwo">Click me</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
  name: 'HomeView',
  setup(){
    const ninjaOne = ref({name: 'mario', age: 30})
    const ninjaTwo = reactive({name: 'luigi', age: 40})

    const nameOne = ref('mario')
    const nameTwo = reactive('luigi')
    
    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }
    
    const updateNinjaTwo = () => {
      ninjaTwo.age = 45
    }

    return { ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo, nameOne, nameTwo }
  }
}
</script>
