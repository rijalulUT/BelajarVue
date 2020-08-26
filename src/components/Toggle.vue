<template>
  <div>
        {{ message }}
        <button @click='hello' v-bind:disabled="loading" v-bind:id="id_custom">{{message}}</button>

        <form action="" @submit.prevent="onSubmit">
            <input v-model="name">{{name.toUpperCase()}} <br>
            <input type="number" v-model.number="satu">{{satu}}<br>
            <input type="number" v-model.number="dua">{{dua}}<br>
            hasil pake click= {{hasil}}<br>
            hasil gak pake click = {{satu+dua}}
            <br>
            <button type="submit">
                Submit Data   
            </button>
        </form>
      </div>
</template>

<script>
export default {
    data(){
        return {
            message: 'Hello Vue!',
            toggle : true,
            loading: true,
            id_custom:"test",
            name:"",
            satu:0,
            dua:0,
            hasil:0
        }
      
    },
    methods: {
        hello(){
            this.toggle  = !this.toggle
            this.message = this.toggle ? "hello" : "enggak hello"
            this.toggle ? alert("hello") : alert("enggak hello")
            this.id_custom = "click"
        },
        onSubmit(){
            this.name
            this.satu 
            this.dua
            this.hasil = this.satu + this.dua
        }
    },
    created(){
            setTimeout(()=>{
               this.loading = false
               this.message = "sudah diubah dalam 5 detik"
               this.id_custom = "ready"
            },5000)
    }
}
</script>

<style>

</style>