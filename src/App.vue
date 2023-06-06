<script>
import { store } from './store';
import axios from 'axios'
import AppHeader from './components/AppHeader.vue'
import ListCards from './components/ListCards.vue'
import AppLoading from './components/AppLoading.vue'
import AppFilter from './components/AppFilter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    ListCards,
    AppLoading,
    AppFilter

  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCards() {
      axios.get(store.apiURL)
        .then(card => {
          store.listCards = card.data.data;
          console.log(store.listCards);
          store.loading = false
        })
        .catch(error => {
          console.log(error);
        })
    },

  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <AppHeader message="Yu-Gi-Oh Api" />
  <AppFilter />
  <AppLoading v-if="store.loading" />
  <ListCards />
</template>

<style lang="scss"></style>
