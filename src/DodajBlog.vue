<template lang="html">
  <div class="row" id="aaa">
    <form class="col s12">
      <div class="row">
        <div class="input-field col s6">
          <i class="material-icons prefix">mode_edit</i>
          <input id="naslov" type="text" length="50" class="validate" v-model="naslov"></input>
          <span class="character-counter black-text" style="float: right; font-size: 12px; height: 1px;"></span>
          <label for="naslov">Naslov bloga</label>

       </div>
     </div><br>
    <div class="row">
      <div class="input-field col s12">
      <i class="material-icons prefix">mode_edit</i>
      <textarea id="textArea" class="materialize-textarea" length="500" v-model="text" ></textarea>
      <label for="textArea">Blog</label>
      <button class="btn waves-effect waves-light" type="submit" name="action" @click.prevent="dodajBlog">Dodaj Blog</button>

     </div>
    </div>
  </form>
</div>
</template>

<script>
export default {
  data: function(){
    return{
      naslov:'',
      text:''
    }
  },
  methods:{
    dodajBlog(){
      if((this.naslov == '')||(this.text == '')){
        if(this.naslov == ''){
          alert("Popunite naslov");
        }else {
          alert("Popunite text");
        }
      } else {
    axios.post("http://741a121.mars-e1.mars-hosting.com/api/blog",{naslov: this.naslov, text: this.text})
    alert("Blog je uspesno dodat!!!");
    this.naslov = '';
    this.text = '';
  }
  }
    }



}
</script>

<style>
 #naslov {
   font-weight: bold;
 }
 #aaa{
   min-height: 470px;
 }
</style>
