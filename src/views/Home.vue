<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-ur-vote">Silahkan Berikan Penilaian</h3>
      <div class="emoticons">
        <Vote :voteProp="vote" />
        </div>
    </section>

    <section class="finish">
      <transition name="fade">
      <h4 v-if="show">Terimakasih Atas Penilaian Anda</h4>
      </transition>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Vote from "@/components/Vote.vue";

export default {
  name: "Home",
  data: function(){
    return{
      show: false
    }
  },
  components: { Vote },
  methods:{
    vote(){
      this.show = true;
    }
  }
};
</script>

<style type="text/css">
  .container {
    display: flex;
    height: 100vh;
    flex-wrap: wrap;
    align-items: center;
  }

  section {
    width: 100%;
  }

  .finish{
    position: absolute;
    bottom: 20px;
  }

  .give-ur-vote{
    font-size: 24px;
  }

  .fade-enter-active, .fade-leave-active{
  transition: opacity 1.5s;
  }
  .fade-enter, .fade-leave-to{
  opacity: 0;
  }
</style>
