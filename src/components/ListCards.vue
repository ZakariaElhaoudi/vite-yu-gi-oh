<script>
import { store } from '../store';
import SingleCard from './SingleCard.vue'
export default {
    name: "ListCards",
    components: {
        SingleCard,
    },
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <main class="py-4">
        <div class="container bg-light py-4 px-4">
            <div class="row bg-dark mx-4">
                <h3>Foun {{ store.listCards.length }} cards</h3>
            </div>
            <div class="row text-center mx-4">
                <SingleCard v-for="card in store.listCards" :details="card" />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

main {
    background-color: $primary;
}

h3 {
    color: white;
}
</style>
