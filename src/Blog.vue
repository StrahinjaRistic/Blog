<template lang="html">
  <div>
  <div class="container">
    <h3>Blogovi</h3>
  </div>
  <div class="parallax-container">
  <div class="parallax"><img src="https://images.unsplash.com/photo-1517245480009-64056ebabb49?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=653cf6c62e246fe1905830fd0c8b12ad&w=1000&q=80"></div>
</div><br>
  <div class="container">
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
.parallax-container {
  height: 500px;
}
</style>
