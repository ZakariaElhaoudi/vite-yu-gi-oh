<script>
import axios from 'axios';
export default {
    name: "AppFilter",
    data() {
        return {
            listCharater: [],
            selectedOption: null,
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
        },
        getArchetype() {
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php=${selectedOption}')
                .then(response => {
                    const archetype = response.data;
                    console.log(archetype);
                })
                .catch(error => {
                    console.log(error);
                })
        }


    },
    mounted() {
        this.getCharaters();
    }
}
</script>

<template>
    <div class="bg_">
        <div class="container">
            <div class="row">
                <div class="col-12  pt-3">
                    <select v-model="selectedOption" @click="getArchetype" name="filter" id="filter">
                        <option v-for="character in listCharater" :value="character" :key="character">
                            {{ character.archetype_name }}
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