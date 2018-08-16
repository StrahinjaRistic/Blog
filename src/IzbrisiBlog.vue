<template lang="html">
  <div>
    <ul>
      <li v-for="blog in blogList">{{blog.blo_naslov}} <button @click="obrisiBlog(blog.blo_id)">X</button> </li>
    </ul>
  </div>
</template>

<script>
export default {
  data:function(){
    return{
      blogList:[]
    }
  },
  mounted(){
    this.poziv();
  },
  methods:{
    obrisiBlog(index){
      axios.delete("http://741a121.mars-e1.mars-hosting.com/api/blog",{ params:{id:index} })
      .then(()=>{
        this.poziv();
      })
    },
    poziv(){
      axios.get("http://741a121.mars-e1.mars-hosting.com/api/blog")
      .then(response => {
        this.blogList = response.data.rezultat;
      });
    }
  }
}
</script>

<style lang="css">
</style>
