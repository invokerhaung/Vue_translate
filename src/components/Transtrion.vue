<template xmlns:v-on="http://www.w3.org/1999/xhtml">
<div class="row" id="transtrion" >
  <div class="col-md-6 col-md-offset-3">
   <form  id="transForm" class="well form-inline" v-on:submit="formSubmit">

     <input type="text" class="form-control" v-model="textToTranslate" placeholder="输入需要的内容">
     <select class="form-control" v-model="language">
       <option value="en" selected="selected">Enlish</option>
       <option value="ru">俄语</option>
       <option value="ja">日语</option>
       <option value="ko">韩语</option>
     </select>
      <input class="btn btn-primary" type="submit" value="翻译">

   </form>
  </div>
</div>
</template>
<script>
  export default{
    name: 'transtrion',
    data(){
      return {
        textToTranslate: "",
        language:""
      };
    },
    methods: {
      formSubmit: function (e) {
//        alert(this.textToTranslate
        //事件注册
        this.$emit("formSubmit",this.textToTranslate,this.language);
        e.preventDefault();
      }
    },
    created:function(){
      this.language = "en";
    }
  };

</script>
<style>
  #transForm{
    -webkit-border-radius:10px;
    -moz-border-radius:10px;
    border-radius:10px;
    border:1px #ccc solid;
  }
</style>
