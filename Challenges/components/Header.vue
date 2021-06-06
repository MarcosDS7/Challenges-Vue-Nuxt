<template>
  <header class="flex justify-between items-center mb-10">
    <div class="container flex flex-col md:flex-row md:justify-between md:items-center">
    <nuxt-link to="/" class="p-4 text-center">Challenges</nuxt-link>

      <nav>
        <ul class="flex flex-col md:flex-row items-center">
          <li class="m-4"><nuxt-link to="/challenge1" class="p-4">Desafio 1</nuxt-link></li>
          <li class="m-4"><nuxt-link to="/challenge2" class="p-4">Desafio 2</nuxt-link></li>
          <li class="m-4"><nuxt-link to="/challenge3" class="p-4">Desafio 3</nuxt-link></li>
          <li class="m-4"><nuxt-link to="/challenge4" class="p-4">Desafio 4</nuxt-link></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.container{
  height: 90px;

  border-radius: 4px;
  background-color: #202020;
  color: #fff;
}


@media only screen and (max-width: 883px) {
  /* Configurações do mobile*/
header{
  height: auto;
}
.container{
  height: auto;
}
}
</style>

<script>
export default {
  
}
</script>