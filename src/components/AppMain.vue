<script>
import FictionList from './FictionList.vue';

export default {
    components: { FictionList }
}
</script>

<template>
    <main>
        <h2>Film:</h2>
        <FictionList :content="'movies'" />
        <h2>Serie TV:</h2>
        <FictionList :content="'series'" />
    </main>
</template>