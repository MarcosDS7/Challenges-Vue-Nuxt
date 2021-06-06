<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@200;300;400;600;700;900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&display=swap');
/* 
font-family: 'Cairo', sans-serif;
font-family: 'Poppins', sans-serif; */

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
html{
  height: 100vh;
}
body{
  height: 100%;
 font-family: 'Poppins', sans-serif; 
}

ul, ol ,a{
  list-style: none;
  text-decoration: none;
}

img{
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
}

.container{
  width: 960px;
  margin: 0 auto;
  box-sizing: border-box;
}
@media only screen and (max-width: 883px) {
  /* Configurações do mobile*/
  .container {
    width: 100%;
  }
}
</style>
