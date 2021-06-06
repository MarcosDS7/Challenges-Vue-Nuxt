<template> 
<section class="container p-5">
<ul class="grid grid-cols-2 md:grid-cols-3 grid-rows-5 md:grid-rows-4 gap-5">
  <li v-for="item of items" :key="item.text" class="bg-gray-50 rounded-md flex flex-col">
   <img class="rounded-md" :src="item.url" alt="Imagem aleatória">
   <p class="p-1">{{ item.text }}</p>
  </li>
</ul>

</section>
</template>

<script>
export default {
  data (){
    return{
      items:[
        { url: "https://picsum.photos/id/6/200/150" , text: "👻 Foto aleatoria 1" },
        { url: "https://picsum.photos/id/16/200/150" , text: "👻 Foto aleatoria 2" },
        { url: "https://picsum.photos/id/26/200/150" , text: "👻 Foto aleatoria 3" },
        { url: "https://picsum.photos/id/46/200/150" , text: "👻 Foto aleatoria 4" },
        { url: "https://picsum.photos/id/56/200/150" , text: "👻 Foto aleatoria 5" },
        { url: "https://picsum.photos/id/66/200/150" , text: "👻 Foto aleatoria 6" },
        { url: "https://picsum.photos/id/76/200/150" , text: "👻 Foto aleatoria 7" },
        { url: "https://picsum.photos/id/85/200/150" , text: "👻 Foto aleatoria 8" },
        { url: "https://picsum.photos/id/96/200/150" , text: "👻 Foto aleatoria 9" },
        { url: "https://picsum.photos/id/106/200/150" , text: "👻 Foto aleatoria 10" },
        { url: "https://picsum.photos/id/116/200/150" , text: "👻 Foto aleatoria 11" },
        { url: "https://picsum.photos/id/126/200/150" , text: "👻 Foto aleatoria 12" }
      ]
    }
  }
};
</script>

<style scoped>

</style>