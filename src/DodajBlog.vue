<template lang="html">
  <div>
    <label>Blogovi</label><br>
      <textarea rows="1" cols="20" v-model="naslov"></textarea><br>
      <textarea rows="5" cols="50" v-model="text"></textarea>
      <button @click.prevent="dodajBlog">Dodaj Blog</button>
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

<style lang="css">
</style>
