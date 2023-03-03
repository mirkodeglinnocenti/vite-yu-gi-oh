<template>

    <header class="main-header">
        <div>
            <img src="/Yu-Gi-Oh_Logo.png" alt="">
        </div>
        <div>
            <span>Yu-Gi-Oh Api</span>
        </div>
    </header>

</template>

<script>
export default{

}
</script>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.main-header {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-around;
    padding: 15px;
    background-color: $bg-color-primary;

    img{
        width: 100px;
        display: block;
    }

    span{
        font-size: 30px;
        font-weight: bold;
    }
}

</style>