<template> 
<article id="app" class="w-full">
<section class="container p-5">
 <h1 class="text-center text-5xl font-bold mb-3">Seja uma boa pessoa!</h1>
  <p class="text-center text-2xl text-gray-50">- Faça sua inscrição abaixo -</p>

  <form action="" class="w-full flex flex-col md:flex-row justify-center items-stretch mt-10" v-on:submit.prevent="checkForm" novalidate>
    
   <section class="content w-full md:w-2/4 p-5 bg-gray-50 rounded">
      <div class="flex flex-col mb-5">
        <input type="name" v-model="name" @keypress="isLetter($event)" class="p-2" placeholder=" ">
        <label>Nome<span class="text-red-500">*</span></label>
      </div>

   <div class="flex flex-col">
      <input type="email" v-model="email" class="p-2" placeholder=" ">
      <label>E-mail<span class="text-red-500">*</span></label>
    </div>
  </section>
  
  <button type="submit" class="w-full md:w-32 flex flex-col items-center justify-center bg-black text-white rounded p-5">
    <img class="mb-3" src="../assets/Vector.png" alt="Botão">
    Enviar
  </button>
  </form>



  <!--- Error --->
    <notificationGroup group="error">
      <div
        class="msg fixed inset-0 flex px-4 py-6 pointer-events-none p-6 items-start justify-end"
      >
        <div class="max-w-sm w-full">
          <notification v-slot="{ notifications }">
            <div
              class="flex max-w-sm w-full mx-auto bg-white shadow-md rounded-lg overflow-hidden mt-4"
              v-for="notification in notifications"
              :key="notification.id"
            >
              <div class="flex justify-center items-center w-12 bg-red-500">
                <svg
                  class="h-6 w-6 fill-current text-white"
                  viewBox="0 0 40 40"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M20 3.33331C10.8 3.33331 3.33337 10.8 3.33337 20C3.33337 29.2 10.8 36.6666 20 36.6666C29.2 36.6666 36.6667 29.2 36.6667 20C36.6667 10.8 29.2 3.33331 20 3.33331ZM16.6667 28.3333L8.33337 20L10.6834 17.65L16.6667 23.6166L29.3167 10.9666L31.6667 13.3333L16.6667 28.3333Z"
                  />
                </svg>
              </div>

              <div class="-mx-3 py-2 px-4">
                <div class="mx-3">
                  <span class="text-red-500 font-semibold">{{
                    notification.title
                  }}</span>
                  <p class="text-gray-600 text-sm">{{ notification.text }}</p>
                </div>
              </div>
            </div>
          </notification>
        </div>
      </div>
    </notificationGroup>
    <!--- End error --->

    <!--- Success --->
    <notificationGroup group="success">
      <div
        class="msg fixed inset-0 flex px-4 py-6 pointer-events-none p-6 items-start justify-end"
      >
        <div class="max-w-sm w-full">
          <notification v-slot="{ notifications }">
            <div
              class="flex max-w-sm w-full mx-auto bg-white shadow-md rounded-lg overflow-hidden mt-4"
              v-for="notification in notifications"
              :key="notification.id"
            >
              <div class="flex justify-center items-center w-12 bg-green-500">
                <svg
                  class="h-6 w-6 fill-current text-white"
                  viewBox="0 0 40 40"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M20 3.33331C10.8 3.33331 3.33337 10.8 3.33337 20C3.33337 29.2 10.8 36.6666 20 36.6666C29.2 36.6666 36.6667 29.2 36.6667 20C36.6667 10.8 29.2 3.33331 20 3.33331ZM16.6667 28.3333L8.33337 20L10.6834 17.65L16.6667 23.6166L29.3167 10.9666L31.6667 13.3333L16.6667 28.3333Z"
                  />
                </svg>
              </div>

              <div class="-mx-3 py-2 px-4">
                <div class="mx-3">
                  <span class="text-green-500 font-semibold">{{
                    notification.title
                  }}</span>
                  <p class="text-gray-600 text-sm">{{ notification.text }}</p>
                </div>
              </div>
            </div>
          </notification>
        </div>
      </div>
    </notificationGroup>
    <!--- End Success --->
</section>
</article>
</template>



<style scoped>
.msg{
position: absolute;
right: 0;
top: 20%;
}
img{
  width: 30px;
  height: 30px;
  object-fit: contain;
}
.content div{
  position: relative;
  padding-top: 13px;
}
.content div input {
  border: 0;
  border-bottom: 2px solid lightgrey;
  outline: none;
  min-width: 180px;
  font-size: 16px;
  transition: all .3s ease-out;
  -webkit-transition: all .3s ease-out;
  -moz-transition: all .3s ease-out;
  -webkit-appearance:none;
  border-radius: 0;
}
.content div input:focus {
  border-bottom: 2px solid #3951b2;
}
.content div input::placeholder{
  color: transparent;
}
.content div label{
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  margin-top: 13px;
  transition: all .3s ease-out;
  -webkit-transition: all .3s ease-out;
  -moz-transition: all .3s ease-out;
}

.content div input:required:invalid + label{
  color: red;
}
.content div input:focus:required:invalid{
  border-bottom: 2px solid red;
}
.content div input:required:invalid + label:before{
  content: '*';
}
.content div input:focus + label,
.content div input:not(:placeholder-shown) + label{
  font-size: 13px;
  margin-top: 0;
  color: #3951b2;
}

@media only screen and (max-width: 883px) {
.msg{
top: 40%;
}
}
</style>


<script>
import Vue from "vue";
import Notifications from "vt-notifications";

Vue.use(Notifications);

export default {
  name: "App",
  data() {
    return {
      name: null,
      email: null
    };
  },
  methods: {
    validEmail: function (email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
    checkForm: function () {
      if (!this.name) {
        this.$notify(
          {
            group: "error",
            title: "Erro",
            text: "Insira seu nome corretamente!",
          },
          4000
        );
      } else if (!this.email) {
        this.$notify(
          {
            group: "error",
            title: "Erro",
            text: "Insira seu e-mail!",
          },
          4000
        );
      } else if (!this.validEmail(this.email)) {
        this.$notify(
          {
            group: "error",
            title: "Erro",
            text: "Insira um e-mail válido!",
          },
          4000
        );
      } else if (this.name && this.email) {
        this.$notify(
          {
            group: "success",
            title: "Sucesso",
            text: "Obrigado(a) pelo contato! Retornaremos em breve!",
          },
          4000
        );
        this.name = this.email = "";
      }
    },
    isLetter(e) {
      let char = String.fromCharCode(e.keyCode);
      if (/^[A-Za-z- ]+$/.test(char)) return true;
      else e.preventDefault();
    },
  },
};
</script>
