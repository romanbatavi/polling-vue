<template>
  <div class="buttons">
    <button v-for="(emoticon, index) in emoticons" 
                    :key="index" 
                    :id="emoticon" 
                    class="btn-emoticon">
    </button>
  </div>
</template>

<script>
// @ is an alias to /src
// import Vote from "@/components/Vote.vue";

export default {
  name: "Home",
  components: {  },
  data: function(){
    return {
      emoticons: ['very-bad','bad','ok','good','excellent']
    }
  }
};
</script>

<style type="text/css">
  .buttons{
    display: flex;
  }

  .btn-emoticon{
    background: url('~@/assets/emoticon.png');
    width: 101px;
    height: 100px;
  }
</style>