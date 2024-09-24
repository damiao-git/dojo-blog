<template>
    <h3>{{ post.title }}</h3>
    <p>{{ snippet }}</p>
</template>

<script>
import { computed } from 'vue';

export default {
    props: ['post'],
    setup(props) {
        const snippet = computed(() => {
            return props.post.body.substring(0, 100) + '....' // função usada para limitar a quantidade de caracteres do post.body e atribuir a const snippet
        })
        return { snippet }
    }
}
</script>

<style></style>