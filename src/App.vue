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
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(card => {
        console.log(card);
      })
  }
}
</script>

<template>
  <AppHeader message="Yu-Gi-Oh Api" />
  <ListCards />
</template>

<style lang="scss"></style>
