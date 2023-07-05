<script>
export default {
    data() {
        return {
            searchedTerm: ''
        }
    },
    props: {
        placeholder: String
    },
    emits: ['button-clicked']
}
</script>

<template>
    <div>
        <input type="text" v-model="searchedTerm" :placeholder="placeholder">
        <button @click="$emit('button-clicked', searchedTerm)">Cerca</button>
    </div>
</template>

<style scoped>
input {
    background-color: black;
    border: 1px solid white;
    color: white;
    padding: 5px;
}

button {
    background-color: red;
    color: white;
    padding: 6px;
    border: none;
}
</style>