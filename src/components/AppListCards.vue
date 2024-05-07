<script>
import AppCard from "./AppCard.vue";

export default {
    components: {
        AppCard
    },
    props: {
        cardsArray: Array,
    },
    data() {
        return {

        }
    }
}

</script>

<template>
    <div class="text-center p-5">
        <h2 class="fw-bolder">Rick and Morty App</h2>
    </div>
    <div class="container">
        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 gap-6">
            <div class="p-2 col " v-for="card in cardsArray">
                <AppCard :cardObj="card" />
            </div>
        </div>

    </div>
</template>

<style lang="scss" scoped></style>