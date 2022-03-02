<template>

  <div>
    <b-button
     variant="light"
     :style="{border:0, background:none}"
     @click="showModal">
      <b-carousel
       id="carousel-1"
       v-model="slide"
       :interval="4000"
       background="#ababab"
       img-width="480"
       img-height="480"
       style="background-color:rgba(255, 255, 255);"
       @sliding-start="onSlideStart"
       @sliding-end="onSlideEnd"
      >
    
    <!--indicators:画像の下部の枚数表示
        controls:画像の切り替え左右ボタン-->
    
      <!-- Text slides with image -->
      
      <b-carousel-slide
        caption="First slide"
        text="Nulla vitae elit libero, a pharetra augue mollis interdum."
        img-src="/img/iOS の画像 (2).jpg"
        
        img-height="480"
        data-toggle="modal" data-target="#my-modal">
      </b-carousel-slide>
      

       
      <!-- Slides with custom text -->
     
      <b-carousel-slide img-src="/img/5C25C2F3-3FDC-43DC-8F13-3DE06BF0453F.jpg"
       
       img-height="480"
       data-toggle="modal" data-target="#my-modal">
        <h1>Hello world!</h1>
      </b-carousel-slide>
     
     

      <!-- Slides with image only -->
     
      <b-carousel-slide img-src="/img/8E79B5B8-95B7-491C-8B59-5BCE866735BC.JPG" 
        
        img-height="480" data-toggle="modal" data-target="#my-modal"></b-carousel-slide>
     
      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
     
     
      <!--<b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            
            height="480"
            src="https://picsum.photos/1024/480/?image=55"
            alt="image slot"
            style="margin: 10px 5px;"
            data-toggle="modal" data-target="#my-modal"
          >
        </template>
      </b-carousel-slide>-->
     

      <!-- Slide with blank fluid image to maintain slide aspect ratio -->
      
      <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image"  data-toggle="modal" data-target="#my-modal">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse eros felis, tincidunt
          a tincidunt eget, convallis vel est. Ut pellentesque ut lacus vel interdum.
        </p>
      </b-carousel-slide>
      

      <b-modal ref="my-modal" size="lg" hide-footer title="Using Component Methods">
        <div class="d-block text-center" >
            <h2>料理名</h2>
            <h5>料理の説明</h5>
        </div>
        <div class="bottun">
        <b-button class="mt-3" variant="outline-info" block><i class="fas fa-star"></i>レシピへ</b-button>
        <b-button :pressed.sync="myToggle" variant="outline-warning" block><i class="fas fa-star"></i>お気に入り</b-button>
        <b-button class="mt-2" block @click="hideModal">閉じる</b-button>
        </div>
      </b-modal>

    </b-carousel>
    </b-button>


    <p class="mt-4">
      Slide #: {{ slide }}<br>
      Sliding: {{ sliding }}
    </p>
  </div>

</template>
<script>
  export default {
    data() {
      return {
        slide: 0,
        sliding: null,
        myToggle: false,
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      },
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
.bottun{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: flex-end;

}
</style>
