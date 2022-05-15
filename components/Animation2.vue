<template>
<transition appear>
  <div class="topPage">
      <nuxt-link to="/recip/"  class="box">welcome to おかしやさん</nuxt-link>
  </div>
</transition>
</template>


<style>
html {
 font-family: 'Pacifico', cursive;
}

.topPage {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box{
  padding: 30px 30px;
  width: 30%;
  position: relative;
  text-align: center;
  display: inline-block;
  color: #fff;
  border: 1px solid #8ed3c9;
  background: #8ed3c9;
  transition: 0.3s
}

.box:hover{
  transform: perspective(500px) translateZ(50px);
}

a:hover {
    color: white;
    text-decoration: none;
}


</style>
