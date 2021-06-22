<template>
    <div class="v-cart-item">
      <img :src=" require('../assets/images/' + cart_item_data.image) " class="cart_item_data__image" alt="img">
      <div class="v-cart-item__info">
        <p>{{cart_item_data.name}}</p>
        <p>{{cart_item_data.price}}</p>
        <p>{{cart_item_data.article}}</p>
      </div>
      <div class="v-cart-item__quantity">
      <p>Qty:</p>
      <span @click="decrementItem">-</span>
      <p>{{cart_item_data.quantity}}</p>
      <span @click="incrementItem">+</span>
      </div>
      <button @click="deleteFromCart">Delete</button>
    </div>
</template>

<script>


export default {
    name:'v-cart-item',
    props:{
        cart_item_data:{
            type:Object,
            default(){
                return {}
            }
        }
    },
    data(){
        return {

        }
    },
    computed:{
        
    },
    methods:{

        deleteFromCart(){
            this.$emit('deleteFromCart');
        },
        decrementItem(){
            this.$emit('deleteFromCart');
        },
        incrementItem(){
            this.$emit('incrementFromCart');
        }
    }
}
</script>

<style lang="scss" scoped>
    .v-cart-item{
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: nowrap;
        flex-basis:25%;
        box-shadow: 0 0 8px #e0e0e0;
        padding: $padding * 2;
        margin-bottom:$margin*2;
        &__image{
            max-width: 50px;
        }
    }

</style>