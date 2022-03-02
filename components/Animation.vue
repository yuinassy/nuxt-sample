<template>
    <div>
        <button class="icobutton icobutton-9-grey-purple"><span class="fa fa-thumbs-up"></span></button>
        <button class="icobutton icobutton-14-grey-pink"><span class="fa fa-heart"></span></button>
    </div>
</template>
<script>
export default {
    head(){
        return{
            script:[
            { src: 'https://photoshopvip.net/wp-content/themes/15zine_ver_2-child/js/animocons.min.js'},
            { src: "animocons.min.js"}
            ],
            link:[
            { rel: 'stylesheet', href: 'https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css'},
            { rel: 'stylesheet', href: 'animocons.min.css'}
            ]
        }
    }
}
</script>
<style scoped>
div{
  position: absolute;
  left: 0%;
  transform: translateY(-50%);
  text-align: center;
}
.icobutton {
  font-size: 3em;
  margin: 0 0.5em
}
</style>