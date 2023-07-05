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
        <BaseSearchbar @button-clicked="searchTerm" />
    </header>
</template>