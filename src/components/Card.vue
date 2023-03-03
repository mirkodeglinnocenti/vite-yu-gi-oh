<template>
    <li>
        <img :src="card.card_images[0].image_url" alt="">
        <p>{{card.name}}</p>
    </li>
</template>

<script>
export default{
    props:{
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss" scoped>
</style>