<template>
    <main class="main">
        <div class="container">
            <ul class="card-list">
                
                <Card v-for="card in store.cards" :key="card.id" :card="card" />
                
            </ul>
        </div>
    </main>
</template>

<script>
// Axios serve per le api
import axios from 'axios';
// Card è un componente
import Card from './Card.vue';
// store è dove si trovano le info date dalle api
import store from '../store';

export default{
    components:{
        Card,
    },
    data(){
        return{
            // cards: [],
            store,
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

                // this.cards = res.data.data;
                this.store.cards = res.data.data;

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
    background-image: url('https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/084d243d-e248-4e6c-8877-21895886b8bb/d7xwheu-a54f38fb-ac20-48d5-a7c8-893ccd06701b.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzA4NGQyNDNkLWUyNDgtNGU2Yy04ODc3LTIxODk1ODg2YjhiYlwvZDd4d2hldS1hNTRmMzhmYi1hYzIwLTQ4ZDUtYTdjOC04OTNjY2QwNjcwMWIucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.5lDicK3YzccLUhMNmIbm52s0J54ukQozFesqL3X2ojE');
}

.card-list{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 15px;

}

</style>