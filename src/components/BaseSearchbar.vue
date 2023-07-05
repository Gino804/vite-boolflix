<script>
export default {
    data() {
        return {
            searchedTerm: ''
        }
    },
    emits: ['button-clicked']
}
</script>

<template>
    <input type="text" v-model="searchedTerm">
    <button @click="$emit('button-clicked', searchedTerm)">Cerca</button>
</template>