<template>
  <div class="home">
    <h1>home</h1>
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      {{ name }}
    </div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue';

export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])

    const stopWatch = watch(search, () => {
      console.log('watch function ran');
    })

    const stopEffect = watchEffect(()=> {
      console.log('watchEffect function ran', search.value);
      
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }
    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
      // essa função faz um filtro dentro dos valores da const names, esse filtro vai buscar dentro de names, tudo que tiver a ver com o valor digitado
      // dentro da const search, que está atribuida a um input type text
    })
    return { names, search, matchingNames, handleClick }
  }
}
</script>
