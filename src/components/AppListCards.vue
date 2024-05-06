<script>
export default {
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
   <div class="container">
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4">
        <div class="col" v-for="card in cardsArray">
            ciao
        </div>
    </div>

   </div>
</template>

<style lang="scss" scoped></style>