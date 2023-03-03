<template>
    <main class="main">
        <div class="container">
            <ul class="card-list">
                
                <Card v-for="card in cards" :key="card.id" :card="card" />
                
            </ul>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';

export default{
    components:{
        Card,
    },
    data(){
        return{
            cards: [],
        }
    },
    methods:{
        fetchCard(){
            axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
            .then((res) => {
                // console.log(res);
                // console.log(res.data);
                // console.log(res.data.data);

                this.cards = res.data.data;

            })
        }
    },
    created(){
        this.fetchCard()
    }

}
</script>

<style lang="scss" scoped>
@use '../style/partials/variables' as *;

.main{
    padding: 40px;
}

.card-list{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 15px;

}

</style>