<script>
import { store } from '../store';
import axios from 'axios';
export default {
    name: "AppFilter",
    data() {
        return {
            store,
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
        },
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
                    <select v-model="store.selectedOption" @change="$emit('getArchetype')" name="filter" id="filter">
                        <option v-for="(character, index ) in listCharater" :value="character.archetype_name" :key="index">
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