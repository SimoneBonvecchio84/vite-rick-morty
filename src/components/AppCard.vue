<script>
export default {
    props: {
        cardObj: Object,
    }
}
</script>

<template>
   <div class="ms_card">
    <img
     class="img-fluid rounded-circle"
    :src="cardObj.image" alt="CurImage">
       <h4>{{ cardObj.name }}</h4>
       <h6>{{ cardObj.status }}</h6>
       <h6>{{ cardObj.species }}</h6>
   </div>
</template>

<style lang="scss" scoped>
.ms_card {
    text-align: center;
}
</style>