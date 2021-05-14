<template>
    <div class="item-container">
        <img :src="require(`@/assets/images/${item.image}`)" alt="">
        <div class="text-container">
            <h4> {{item.title}} </h4><button class="xt-1" variant="outline-danger" block @click="() => {
                    remove(item.id) 
        
      }">Remove</button>
            <p> {{item.description}} </p>
        </div>
    </div>
</template>

<script>
import {mapMutations} from "vuex"
    export default {
        props: ['item'],
        methods: {
            ...mapMutations(['removeItem']),
            remove(id) {
                 if(confirm("Do you really want to delete?")){
                       this.removeItem(id) 
                    }
                },
    }
    }
</script>

<style scoped>
    .item-container {
        display: flex;
        margin: 3rem 0
    }
    .text-container {
        padding: 0 1rem
    }
    img {
        width: 17.5rem;
        border-radius: 0.5rem;
        height: 11rem
    }
    p {
        font-size: 0.8rem;
        color: grey
    }
</style>