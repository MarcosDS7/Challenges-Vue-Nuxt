<template>

<article class="w-full p-5">
 <form action="" class="container flex flex-col" v-on:submit="registrar">
      <label for="inputCep">CEP</label>
      <input class="w-full p-2 rounded mb-2" id="inputCep" type="text" v-model="cep" v-on:keyup="buscar">

      <div class="col-md-3"><span class="text-danger" v-show="naoLocalizado"><strong>* CEP não encontrado</strong></span></div>

      <label for="inputLogradouro">Endereço</label>
      <input class="w-full p-2 rounded mb-2" id="inputLogradouro" type="text" v-model="endereco.logradouro">

      <label for="inputBairro">Bairro</label>
      <input class="w-full p-2 rounded" id="inputBairro" type="text" v-model="endereco.bairro">

      <label for="inputCidade">Cidade</label>
      <input class="w-full p-2 rounded" id="inputCidade" type="text" v-model="endereco.localidade">
      
      <label for="inputEstado">Estado</label>
      <input class="w-full p-2 rounded" id="inputEstado" type="text" v-model="endereco.uf" maxlength="2">

    </form>
</article>
</template>


<script>

export default {
  data () {
    return{
    cep: '',
    endereco: {},
    naoLocalizado: false
    }
  },
  mounted: function () {
    $("#inputCep").mask("00000-000");
  },
  methods: {
    registrar: function(){
      // processar dados
    },
    buscar: function(){
      var self = this;
      
      self.naoLocalizado = false;
      
      if(/^[0-9]{5}-[0-9]{3}$/.test(this.cep)){
        $.getJSON("https://viacep.com.br/ws/" + this.cep + "/json/", function(endereco){
          if(endereco.erro){
            self.endereco = {};
            $("#inputLogradouro").focus();
            self.naoLocalizado = true;
            return;
          }
          self.endereco = endereco;
          console.log(endereco);
          $("#inputNumero").focus();
        });
      }
    }
  }
}

</script>