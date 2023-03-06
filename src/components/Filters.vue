<template>
<div class="container">
    <input @keyup.enter="$emit('onInput')" v-model="store.inputValue" type="text" placeholder="Inseresci un nome">
</div>

</template>




<script>

import store from '../store';

export default{
    data (){
        return{
            store,
        }
    }
}
</script>




<style lang="scss" scoped>

input{
    font-size: 18px;
    padding: 5px;
}

</style>