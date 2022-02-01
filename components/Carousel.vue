<template>

  <div>
    <b-button @click="showModal">
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
    >
    <!--indicators:画像の下部の枚数表示
        controls:画像の切り替え左右ボタン-->
    
      <!-- Text slides with image -->
      
        <b-carousel-slide
          caption="First slide"
          text="Nulla vitae elit libero, a pharetra augue mollis interdum."
          img-src="/img/iOS の画像 (2).jpg"
          data-toggle="modal" data-target="#my-modal">
        </b-carousel-slide>
      

       
      <!-- Slides with custom text -->
     
      <b-carousel-slide img-src="/img/5C25C2F3-3FDC-43DC-8F13-3DE06BF0453F.jpg"
      data-toggle="modal" data-target="#my-modal">
        <h1>Hello world!</h1>
      </b-carousel-slide>
     
     

      <!-- Slides with image only -->
     
      <b-carousel-slide img-src="/img/8E79B5B8-95B7-491C-8B59-5BCE866735BC.JPG" data-toggle="modal" data-target="#my-modal"></b-carousel-slide>
     
      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
     
     
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="https://picsum.photos/1024/480/?image=55"
            alt="image slot"
            data-toggle="modal" data-target="#my-modal"
          >
        </template>
      </b-carousel-slide>
     

      <!-- Slide with blank fluid image to maintain slide aspect ratio -->
      
      <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image" data-toggle="modal" data-target="#my-modal">
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
              <b-button class="mt-3" variant="outline-info" block><i class="fas fa-star"></i>レシピへ</b-button>
              <div class="btn-group-toggle" data-toggle="buttons">
                <label class="btn btn-outline-warning">
                  <input type="checkbox" checked autocomplete="off"> <i class="fas fa-star"></i>お気に入り
                </label>
              </div>
              <input id="btn-check-outlined" type="checkbox" class="btn-check"  autocomplete="off">
                <label class="btn btn-outline-primary" for="btn-check-outlined">Single toggle</label><br>
              <b-button class="mt-2" block @click="hideModal">閉じる</b-button>
              <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">
  <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off">
  <label class="btn btn-outline-primary" for="btncheck1">Checkbox 1</label>

  <input type="checkbox" class="btn-check" id="btncheck2" autocomplete="off">
  <label class="btn btn-outline-primary" for="btncheck2">Checkbox 2</label>

  <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off">
  <label class="btn btn-outline-primary" for="btncheck3">Checkbox 3</label>
</div>
<div class="btn-group-toggle" data-toggle="buttons">
  <label class="btn btn-warning active">
    <input type="checkbox" checked autocomplete="off"> Checked
  </label>
</div>
<button class="btn btn-primary" data-toggle="button" aria-pressed="false" autocomplete="off">Toggle</button>

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
        sliding: null
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
