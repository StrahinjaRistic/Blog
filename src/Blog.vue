<template lang="html">
  <div class="container">
    <h3>Blogovi</h3>
    <hr>
    <div class="row">
      <div v-for="blog in blogList" class="col s12">
        <div class="card">
          <div class="card-content">
            <span class="card-title">{{blog.blo_naslov}}</span>
            <p>{{blog.blo_text}}</p>
          </div>
        </div>
      </div>
    </div>
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
      axios.get("http://741a121.mars-e1.mars-hosting.com/api/blog")
      .then(response => {
      this.blogList = response.data.rezultat;
      });
    }
}

</script>

<style scoped>
.card-title{
  font-size: 30px;
}
.card-content p {
  font-size: 18px;
}
</style>
