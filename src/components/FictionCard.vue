<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        rating: Number,
        poster: String
    },
}
</script>

<template>
    <ul>
        <li><img :src="`https://image.tmdb.org/t/p/w342${poster}`" :alt="title"></li>
        <li>Titolo: {{ title }}</li>
        <li>Titolo originale: {{ originalTitle }}</li>
        <li>Lingua: <img :src="`../src/assets/img/${language}.png`" :alt="language"></li>
        <li>Valutazioni:
            {{ rating }}</li>
    </ul>
</template>