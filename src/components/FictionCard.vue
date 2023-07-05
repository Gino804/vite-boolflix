<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        rating: Number,
        poster: String,
        overview: String
    },
    data() {
        return {
            roundedRating: Math.ceil(this.rating / 2)
        }
    }
}
</script>

<template>
    <div class="card">
        <img :src="`https://image.tmdb.org/t/p/w342${poster}`" :alt="title">
        <div>
            <h4>{{ title }}</h4>
            <p><b>Titolo originale: </b>{{ originalTitle }}</p>
            <p><b>Lingua: </b><img :src="`../src/assets/img/${language}.png`" :alt="language"></p>
            <p><b>Valutazione:</b>
                <i :class="roundedRating ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
                <i :class="roundedRating >= 2 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
                <i :class="roundedRating >= 3 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
                <i :class="roundedRating >= 4 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
                <i :class="roundedRating === 5 ? 'fa-solid' : 'fa-regular'" class="fa-star"></i>
            </p>
            <p><b>Trama:</b> {{ overview }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    position: relative;

    * {
        margin-top: 10px;
    }

    >img {
        width: 100%;
        padding: 10px;
    }

    div {
        background-color: black;
        position: absolute;
        top: 10px;
        bottom: 10px;
        left: 10px;
        right: 10px;
        display: none;
        text-align: center;
        color: white;
        padding: 20px 10px;
        overflow: auto;

        h4 {
            font-size: 24px;
        }

        img {
            height: 12px
        }
    }

    &:hover {
        div {
            display: block;
        }
    }
}
</style>