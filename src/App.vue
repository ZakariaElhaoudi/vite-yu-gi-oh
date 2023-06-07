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
    getArchetype() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&${selectedOption}')
        .then(response => {
          const archetype = response.data.
            console.log(archetype);
        })
        .catch(error => {
          console.log(error);
        })
    }

  },
  created() {
    this.getCards();
    this.getArchetype();
  }
}
</script>

<template>
  <AppHeader message="Yu-Gi-Oh Api" />
  <AppFilter @getArchetype="getArchetype" />
  <AppLoading v-if="store.loading" />
  <ListCards />
</template>

<style lang="scss"></style>
