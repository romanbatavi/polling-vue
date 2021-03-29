<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-ur-vote">Silahkan Berikan Penilaian</h3>
      <div class="emoticons">
        <Vote />
        </div>
    </section>

    <section class="finish">
      <h4>Terimakasih Atas Penilaian Anda</h4>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Vote from "@/components/Vote.vue";

export default {
  name: "Home",
  components: { Vote },
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
</style>
