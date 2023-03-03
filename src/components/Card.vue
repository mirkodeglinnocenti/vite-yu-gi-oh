<template>
    <li class="card-box">
        <img :src="card.card_images[0].image_url" alt="">
        <p>{{card.name}}</p>
        <span>{{ card.archetype }}</span>
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
@use '../style/partials/variables' as *;
.card-box{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    background-color: $bg-color-primary;

    p{
        font-size: 1.2rem;
        text-align: center;
        color: white;
    }

    span{
        margin-top: auto;
        font-weight: 600;
        margin-bottom: 10px;
    }
    
}

</style>