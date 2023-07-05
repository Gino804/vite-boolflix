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
    <BaseSearchbar @button-clicked="searchTerm" />
</template>