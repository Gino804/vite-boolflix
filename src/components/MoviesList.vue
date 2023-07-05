<script>
import MovieCard from './MovieCard.vue';
import { store } from '../data/store';

export default {
    components: { MovieCard },

    data() {
        return { store }
    }
}
</script>

<template>
    <ul>
        <li v-for="movie in store.movies" :key="movie.id">
            <MovieCard :title="movie.title" :original-title="movie.original_title" :language="movie.original_language"
                :rating="movie.vote_average" />
        </li>
    </ul>
</template>