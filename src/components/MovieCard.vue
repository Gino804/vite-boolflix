<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        rating: Number
    }
}
</script>

<template>
    <ul>
        <li>Titolo: {{ title }}</li>
        <li>Titolo originale: {{ originalTitle }}</li>
        <li>Lingua: {{ language }}</li>
        <li>Valutazioni: {{ rating }}</li>
    </ul>
</template>