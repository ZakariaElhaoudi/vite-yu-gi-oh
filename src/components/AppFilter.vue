<script>
import axios from 'axios';
export default {
    name: "AppFilter",
    data() {
        return {
            listCharater: [],

        }
    },
    methods: {
        getCharaters() {
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then(response => {
                    this.listCharater = response.data;
                    console.log(this.listCharater);
                })
                .catch(error => {
                    console.log(error);
                })
        }

    },
    mounted() {
        this.getCharaters(); // Chiamata alla funzione per recuperare i dati quando il componente viene montato
    }
}
</script>

<template>
    <div class="bg_">
        <div class="container">
            <div class="row">
                <div class="col-12  pt-3">
                    <select name="filter" id="filter">
                        <option v-for="character in listCharater" value="character" :key="character">
                            {{ character }}
                        </option>
                    </select>
                </div>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

.bg_ {
    background-color: $primary;
}
</style>