<template>
<transition appear>
  <div class="topPage">
      <nuxt-link to="/recip/"  class="box">welcome to おかしやさん</nuxt-link>
  </div>
</transition>
</template>


<script>
export default {
    transition: "expandFade",
    mode: ''
}
</script>

<style>
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
}




/* @keyframes expandFadeOut {
  
  100% {
    width: 100vw;
    height: 100vh;
  }
} */

/* .expandFade-enter-active {
  transition: opacity 0.8s;
} */

/* .expandFade-leave-active .bnr::before {
  animation: expandFadeOut 0.8s 0s ease-in-out forwards;
} */


/* .expandFade-enter {
  opacity: 0;
} */

.expandFade-enter-active {
  transition: 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.expandFade-enter {
  opacity: 0;
  transform: translate(0%, -5%) scale(0.5, 1.5);
}
</style>
