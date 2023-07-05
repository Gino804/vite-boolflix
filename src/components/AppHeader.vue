<script>
import BaseSearchbar from './BaseSearchbar.vue';

export default {
    components: { BaseSearchbar },
    emits: ['searched-term'],
    methods: {
        searchTerm(searchedTerm) {
            this.$emit('searched-term', searchedTerm);
        }
    }
}
</script>

<template>
    <header>
        <h1>BOOLFLIX</h1>
        <BaseSearchbar @button-clicked="searchTerm" :placeholder="'Cerca film o serie TV'" />
    </header>
</template>

<style scoped>
header {
    background-color: black;
    height: 100px;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 50px;
}

h1 {
    color: red;
    font-size: 40px;
}
</style>