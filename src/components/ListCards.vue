<script>
import SingleCard from './SingleCard.vue'
export default {
    name: "ListCards",
    components: {
        SingleCard,
    }
}
</script>

<template>
    <main class="pt-4">
        <div class="container bg-light">
            <div class="row">
                <div class="col-6"></div>
                <img src="img" alt="img">
                <h3>dati</h3>
                <h3>dati</h3>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

main {
    background-color: $primary;
}
</style>
