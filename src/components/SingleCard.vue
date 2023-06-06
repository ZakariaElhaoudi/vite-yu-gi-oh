<script>
import { store } from '../store';

export default {
    name: "SingleCard",
    props: {
        details: Object
    }
}
</script>

<template>
    <div class="col-4 col-md-3 col-lg-2 card my-2 mx-3">
        <img :src="details.card_images[0].image_url_small" :alt="details.name">
        <h3>{{ details.name }}</h3>
        <h4>{{ details.archetype }}</h4>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

div {
    background-color: $primary ;

    h3 {
        color: $white;
    }
}
</style>
