<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        rating: Number
    },
    data() {
        return {
            imageUrl: `../src/assets/img/${this.language}.png`
        }
    }
}
</script>

<template>
    <ul>
        <li>Titolo: {{ title }}</li>
        <li>Titolo originale: {{ originalTitle }}</li>
        <li>Lingua: <img :src="`../src/assets/img/${language}.png`" :alt="language"></li>
        <li>Valutazioni:
            {{ rating }}</li>
    </ul>
</template>