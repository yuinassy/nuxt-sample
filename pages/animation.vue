<template>
  <Animation2/>

</template>

<script>
export default {
    transition: "expandFade",
    mode: ''
}
</script>

<style>
html {
 font-family: 'Pacifico', cursive;
}
.expandFade-enter-active {
  transition: 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.expandFade-enter {
  opacity: 0;
  transform: translate(0%, -5%) scale(0.5, 1.5);
}


</style>

