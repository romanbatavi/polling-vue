<template>
  <div class="buttons">
    <button v-for="(emoticon, index) in emoticons" 
                    :key="index" 
                    :id="emoticon"
                    :value="emoticon"
                    @click="vote"
                    :disabled="isDisable"
                    :class="{active: emoticon == emoticonClick}"
                    class="btn-emoticon">
    </button>
  </div>
</template>

<script>
// @ is an alias to /src
// import Vote from "@/components/Vote.vue";
import moment from "moment";

export default {
  name: "Vote",
  props: { 
    voteProp :{
      type : Function()
    } 
  },
  data: function(){
    return {
      emoticons: ['very-bad','bad','ok','good','excellent'],
      // isDisable: false,
      emoticonClick: ''
    }
  },
  methods:{
    vote(e){
      var voted = e.target.value;
      // this.isDisable = true;
      this.emoticonClick = voted;
      
      this.store(voted);
      
      this.voteProp();
    },
    store(voted){
      var keyStorage = moment().format('YYYYMMDDhmmss a');
      var create_at = moment().format('YYYY-MM-DD h:mm:ss a');
      var data = {
        vote: voted,
        create_at: create_at
      }

      var jsonToString = JSON.stringify(data);

      localStorage.setItem(keyStorage,jsonToString);
    }
  },
  computed:{
    isDisable : function(){
      return this.emoticonClick.length === 0 ? false : true;
    }
  },
  mounted(){
    this.$root.$on('emitProcess', () => {
      this.emoticonClick = '';
    });
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
    border: none;
    margin: 0px 10px;
    outline: none;
    cursor: pointer;
  }

  .emoticons{
    display: flex;
    justify-content: center;
  }
  /* very-bad */
  #very-bad{
    background-position: 0px 0px;
  }
  #very-bad:hover{
    background-position: 0px -100px;
  }
  #very-bad.active,
  #very-bad:active{
    background-position: 0px -200px;
  }
  /* bad */
  #bad{
    background-position: -101px 0px;
  }
  #bad:hover{
    background-position: -101px -100px;
  }
  #bad.active,
  #bad:active{
    background-position: -101px -200px;
  }
  /* ok */
  #ok{
    background-position: -202px 0px;
  }
  #ok:hover{
    background-position: -202px -100px;
  }
  #ok.active,
  #ok:active{
    background-position: -202px -200px;
  }
  /* good */
  #good{
    background-position: -303px 0px;
  }
  #good:hover{
    background-position: -303px -100px;
  }
  #good.active,
  #good:active{
    background-position: -303px -200px;
  }
  /* excellent */
  #excellent{
    background-position: -404px 0px;
  }
  #excellent:hover{
    background-position: -404px -100px;
  }
  #excellent.active,
  #excellent:active{
    background-position: -404px -200px;
  }
</style>