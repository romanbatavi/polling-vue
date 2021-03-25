<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-ur-vote">Silahkan Berikan Penilaian</h3>
      <div class="emoticons">//Akan Menjadi Emoticon</div>
    </section>

    <section class="finish">
      <h4>Terimakasih Atas Penilaian Anda</h4>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
// import vote from "@/components/vote.vue";

export default {
  name: "Home",
  components: {},
};
</script>

<style type="text/css">
  .container {
    display: flex;
    height: 100hv;
    flex-wrap: wrap;
    align-items: center;
  }

  section {
    width: 100%;
  }
</style>
