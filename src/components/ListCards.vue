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
    <main class="py-4">
        <div class="container bg-light py-2 px-2">
            <div class="row text-center ">
                <div class="col-6 col-md-4 col-lg-3">
                    <img src="img" alt="img">
                    <h3>dati</h3>
                    <h3>dati</h3>
                </div>
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
