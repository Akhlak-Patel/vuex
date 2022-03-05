<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="name" placeholder="Enter name">
        <input type="text" v-model="price" placeholder="Enter price">
        <button type="submit">Add</button>
    </form>
</template>
<script>
import {mapActions} from 'vuex'
export default {
    name:"AddProduct",
    data(){
        return {
            name:'',
            price:''
        }
    },
    methods:{
        ...mapActions(["addProduct"]),
        onSubmit(){
            // console.log(this.name,this.price)
            this.addProduct({
                name:this.name,
                price:this.price
            }),
            this.name='',
            this.price=''
        }
    }
}
</script>