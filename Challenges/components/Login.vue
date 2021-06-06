<template> 
<section class="container p-5">
 <h1 class="text-center text-5xl font-bold mb-3">Seja uma boa pessoa!</h1>
  <p class="text-center text-2xl text-gray-50">- Faça sua inscrição abaixo -</p>

  <form action="" class="flex flex-col md:flex-row justify-center items-stretch mt-10">
   <section class="w-full md:w-2/4 p-5 bg-gray-50 rounded">
      <div class="flex flex-col mb-5">
        <input type="text" name="" id="" class="p-2" placeholder=" " >
        <label for="">Nome<span class="text-red-500">*</span></label>
      </div>

   <div class="flex flex-col">
      <input type="text" name="" id="" class="p-2" placeholder=" ">
      <label for="">E-mail<span class="text-red-500">*</span></label>
    </div>
  </section>
  
  <button type="submit" class="w-full md:w-32 flex flex-col items-center justify-center bg-black text-white rounded p-5">
    <img class="mb-3" src="../assets/Vector.png" alt="Botão">
    Enviar
  </button>
  </form>

</section>
</template>



<style scoped>
img{
  width: 30px;
  height: 30px;
  object-fit: contain;
}
section div{
  position: relative;
  padding-top: 13px;
}
section div input {
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
section div input:focus {
  border-bottom: 2px solid #3951b2;
}
section div input::placeholder{
  color: transparent;
}
section div label{
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  margin-top: 13px;
  transition: all .3s ease-out;
  -webkit-transition: all .3s ease-out;
  -moz-transition: all .3s ease-out;
}

section div input:required:invalid + label{
  color: red;
}
section div input:focus:required:invalid{
  border-bottom: 2px solid red;
}
section div input:required:invalid + label:before{
  content: '*';
}
section div input:focus + label,
section div input:not(:placeholder-shown) + label{
  font-size: 13px;
  margin-top: 0;
  color: #3951b2;
}
</style>