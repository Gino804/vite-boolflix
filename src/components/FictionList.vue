<script>
import FictionCard from './FictionCard.vue';
import { store } from '../data/store';

export default {
    components: { FictionCard },

    data() {
        return { store }
    },

    props: {
        content: String
    }
}
</script>

<template>
    <ul>
        <li v-for="fiction in store[content]" :key="fiction.id">
            <FictionCard :title="content === 'movies' ? fiction.title : fiction.name"
                :original-title="content === 'movies' ? fiction.original_title : fiction.original_name"
                :language="fiction.original_language" :rating="fiction.vote_average" :poster="fiction.poster_path" />
        </li>
    </ul>
</template>