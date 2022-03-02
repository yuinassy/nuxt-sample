<template>
  <div class="lowerPage">
    <h1 class="title">Lower Page</h1>
  </div>
</template>

<script>

</script>


<style>
.lowerPage {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #000;
}

@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}

.title {
  font-size: 30px;
  font-weight: bold;
  text-align: center;
  color: #fff;

  
}
</style>