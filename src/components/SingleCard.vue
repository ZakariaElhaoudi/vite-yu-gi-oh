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
    <div class="col-6 col-md-4 col-lg-3">
        <img :src="details.card_images[0].image_url_small" :alt="details.name">
        <h3>{{ details.name }}</h3>
        <h6>{{ details.archetype }}</h6>
    </div>
</template>

<style lang="scss" scoped></style>
