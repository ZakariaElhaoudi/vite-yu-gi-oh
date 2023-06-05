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
        <div class="container bg-light py-2 px-2">
            <div class="row text-center ">
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
</style>
