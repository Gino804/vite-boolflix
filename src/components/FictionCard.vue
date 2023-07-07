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
    },
    computed: {
        shortOverview() {
            if (this.overview.length > 200) return `${this.overview.substring(0, 200).trim()}...`;
            else return this.overview;
        }
    }
}
</script>

<template>
    <div class="card">
        <img :src="poster ? `https://image.tmdb.org/t/p/w342${poster}` : '../src/assets/img/no-poster.png'" :alt="title">
        <div>
            <h4>{{ title }}</h4>
            <p><b>Titolo originale: </b>{{ originalTitle }}</p>
            <p><b>Lingua: </b><img v-if="language === 'en' || language === 'it'" :src="`../src/assets/img/${language}.png`"
                    :alt="language"><span v-else>{{ language.toUpperCase() }}</span></p>
            <p><b>Valutazione:</b>
                <i v-for="n in 5" :class="roundedRating <= n ? 'fa-regular' : 'fa-solid'" class="fa-star"></i>
            </p>
            <p><b>Trama:</b> {{ shortOverview }}</p>
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