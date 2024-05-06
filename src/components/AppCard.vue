<script>
export default {
    props: {
        cardObj: Object,
    }
}
</script>

<template>
   <div class="ms_card">
    <img :src="cardObj.image" alt="CurImage">
       <h4>{{ cardObj.name }}</h4>
   </div>
</template>

<style lang="scss" scoped>

</style>