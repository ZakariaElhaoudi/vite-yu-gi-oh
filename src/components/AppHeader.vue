<script>
export default {
    name: "AppHeader",
    props: ["message"]
}
</script>

<template>
    <header class="container">
        <div class="row">
            <div class="col-4">
                <img src="../assets/ygoprodeck_logo.png" alt="">
            </div>
            <div class="col-8">
                <h1>{{ message }}</h1>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped></style>
