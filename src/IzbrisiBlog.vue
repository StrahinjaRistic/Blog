<template lang="html">
  <div class="container" id="ab">
    <h2>Blogovi</h2>
    <ul class="collection with-header">
      <li class="collection-header"><h4>Lista blogova</h4></li>
      <li class="collection-item" v-for="blog in blogList">{{blog.blo_naslov}}<button class="material-icons secondary-content" @click="obrisiBlog(blog.blo_id)">delete</button>
        <!-- <button @click="obrisiBlog(blog.blo_id)">X</button> -->
      </li>
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

<style>
#ab{
  min-height: 700px;
}
</style>
