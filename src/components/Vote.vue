<template>
  <div class="buttons">
    <button v-for="(emoticon, index) in emoticons" :key="index" :id="emoticon" class="btn-emoticon"></button>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {},
  data: function(){
    return {
      emoticons: ['very-bad','bad','ok','good','excellent']
    }
  }
};
</script>
