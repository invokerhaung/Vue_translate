<template >
<div id="app" >
  <h1 >在线翻译</h1>
  <h5 class="text-muted">简单//易用//便捷</h5>
<transtrion v-on:formSubmit="translateText"></transtrion>
  <trans-out-put v-text="transletedOutPut"></trans-out-put>
  </div>
</template>

<script>
import Transtrion from './components/Transtrion'
import TransOutPut from './components/TranslateOutPut'
export default {
  name: 'app',
  components: {
    Transtrion,
    TransOutPut
  },
  data(){
      return{
          transletedOutPut:""
      }
  },
  methods:{
    translateText:function (text,lang) {
        this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/" +
          "translate?key=trnsl.1.1.20170915T065513Z.2c27a3e52af6c981.a643f16cf225bc3db082a92b56f454bd1d56e" +
          "b35&lang="+lang+"&text="+text).then(
          (response)=>{
              this.transletedOutPut=response.body.text.toString();
          }
        )
      }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
