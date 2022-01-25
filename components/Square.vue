<template>
  <div>
    <div v-if="sharp==='seihoukei'"
          class="seihoukei"
          :style="{ background: color }"
          @click="changeSharp">
          {{ sharp }}
          
    </div>
    <div v-if="sharp==='maru'"
          class="circle"
          :style="{ background: color }"
          @click="changeSharp">
          {{ sharp }}
          {{ primary }}
          {{ secondary }}
         
        
    </div>


    <div v-if="color==='second'"
          class="yellow">
    </div>

  </div>
</template>
<script>
export default {
  props: {
    sharp: {
      type: String,
   },
    primary: {
      type: String,
    },
    secondary: {
      type: String,
    },
  },
  data () {
    return {
      isActive: true,
      hasError: false,
      color: this.primary      
    }
  },
  methods:{
    changeSharp(){ 
      if(this.color === this.primary){
        this.color = this.secondary;
      }else{
        this.color = this.primary;
      }
    },
  },
}

</script>
<style scoped>
.seihoukei{
  width: 100px;
  height:100px;
  margin-right: 20%; 
  
}
.circle{
  width: 100px;
  height:100px;
  margin-right: 20%;
  border-radius: 50%;
  
  
}


</style>
