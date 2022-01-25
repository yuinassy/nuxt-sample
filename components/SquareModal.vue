<template>

    <div>
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.4.2/css/all.css" integrity="sha384-/rXc/GQVaYpyDdyxK+ecHPVYJSN9bmVFBvjA/9eOB+pb3F2w2N6fc5qB9Ew5yIns" crossorigin="anonymous">

        <div v-if="image==='seihoukei'"
          class="seihoukei"
          b-button id="show"
          :style="{ background: color }"
          @click="showModal">
          {{ image }}

          <b-modal ref="my-modal" hide-footer title="Using Component Methods">
              <div class="d-block text-center">
                  <h3>Hello World!!</h3>
              </div>
              <b-button class="mt-3" variant="warning" block @click="toggleModal"><i class="fas fa-star"></i>お気に入り</b-button>
              <b-button class="mt-2" block @click="hideModal">閉じる</b-button>
          </b-modal>
          
        </div>
    </div>


  

</template>
<script>
export default {
  props: {
    image: {
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

    showModal() {
        this.$refs['my-modal'].show()
    },
    hideModal() {
        this.$refs['my-modal'].hide()
    },
    toggleModal() {
        // We pass the ID of the button that we want to return focus to
        // when the modal has hidden
        this.$refs['my-modal'].toggle('#toggle-btn')
    }
    
  }
}

</script>
<style scoped>
.seihoukei{
  width: 100px;
  height:100px;
  margin-right: 20%;
  background-color:red; 
  
}


</style>