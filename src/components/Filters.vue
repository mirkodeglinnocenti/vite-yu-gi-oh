<template>
<div class="container">
    <div class="filter-box">
        <h3>Ricerca personalizzata</h3>
        <input @keyup.enter="$emit('onInput')" v-model="store.inputValue" type="text" placeholder="Inseresci un nome">
    </div>
    
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

.filter-box{
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 10px;
    padding-bottom: 10px;
    border-bottom: 1px solid white;

    h3{
    color: white;
    }

    input{
        font-size: 18px;
        padding: 5px;
    }

}



</style>