<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        rating: Number,
        poster: String
    },
    data() {
        return {
            roundedRating: Math.ceil(this.rating / 2)
        }
    }
}
</script>

<template>
    <ul>
        <li><img :src="`https://image.tmdb.org/t/p/w342${poster}`" :alt="title"></li>
        <li>Titolo: {{ title }}</li>
        <li>Titolo originale: {{ originalTitle }}</li>
        <li>Lingua: <img :src="`../src/assets/img/${language}.png`" :alt="language"></li>
        <li>Valutazioni:
            <i :class="roundedRating ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
            <i :class="roundedRating >= 2 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
            <i :class="roundedRating >= 3 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
            <i :class="roundedRating >= 4 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
            <i :class="roundedRating === 5 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
        </li>
    </ul>
</template>