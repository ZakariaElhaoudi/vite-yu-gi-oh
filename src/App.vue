<script>
import { store } from './store';
import axios from 'axios'
import AppHeader from './components/AppHeader.vue'
import ListCards from './components/ListCards.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    ListCards,

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
        })
        .catch(error => {
          console.log(error);
        })
    }
  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <AppHeader message="Yu-Gi-Oh Api" />
  <ListCards />
</template>

<style lang="scss"></style>
