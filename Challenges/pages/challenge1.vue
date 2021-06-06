<template> 
<div>
<Header />
<Header-instagram/>
<Cards-Instagram/>
</div>
</template>

<script>
import HeaderInstagram from '../components/Header-Instagram.vue';
export default {
  components: { HeaderInstagram },};
</script>

<style scoped>

div{
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;

  background: linear-gradient(to left bottom, rgb(228, 133, 38), rgb(229, 151, 71), rgb(228, 169, 101), rgb(225, 187, 130), rgb(219, 205, 159));

  background-repeat: no-repeat;
}

</style>