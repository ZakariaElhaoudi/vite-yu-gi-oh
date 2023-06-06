<script>
export default {
    name: "AppFilter",
    data() {
        return {
            store

        }

    }
}
</script>

<template>
    <div class="bg_">
        <div class="container">
            <div class="row">
                <div class="col-12  pt-3">
                    <select v-model="selectedOption" name="filter" id="filter">
                        <option value="Alien">Alien</option>
                        <option value="Dark Magician">Dark Magician</option>
                        <option value="Blue-Eyes">Blue-Eyes</option>
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