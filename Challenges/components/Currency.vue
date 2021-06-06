<template>
 <article class="flex flex-col container">
  <h1 class="text-4xl text-center font-semibold mb-10">USD para BRL</h1>

<form class="w-full md:w-2/4 flex flex-col">
  <label for="" class="text-2x1 mb-2">Valor para conversão</label>
  <input type="text" class="p-2 rounded w-full" v-model="value">
</form>

<button @click="calc" class="btn mt-5">Calcular</button>
<div>
  <p>{{ result }}</p>
</div>

 </article>
</template>

<script>

import Vue from "vue";
import axios from 'axios'

Vue.use(axios)

export default {
  data (){
    return{
      value: '',
      convert: '',
      result: ''
    }
  },
  mounted () {
       axios
        .get(`https://free.currconv.com/api/v7/convert?q=USD_BRL,BRL_USD&compact=ultra&apiKey=1860eeff9d6b141a8308`)
        .then((result) => {
          this.convert = result.data.USD_BRL.toFixed(2)
        })
    },
    methods: {
       calc(){
        this.result = this.value * this.convert
  } 
},
}
</script>

<style scoped>
.btn{
  width: 130px;
  height: 45px;

  border-radius: 5px;
  background-color: #202020;
  color: #fff;
}
</style>
