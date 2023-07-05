<script>
import FictionList from './FictionList.vue';
import { store } from '../data/store';

export default {
    components: { FictionList },

    data() {
        return { store }
    },
}
</script>

<template>
    <div class="container">
        <main v-if="store.movies.length">
            <h2>Film</h2>
            <FictionList :content="'movies'" />
            <h2>Serie TV</h2>
            <FictionList :content="'series'" />
        </main>
    </div>
</template>

<style scoped>
main {
    margin-top: 130px;
}

h2 {
    font-size: 35px;
    color: white;
}
</style>