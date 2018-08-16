<template lang="html">
  <div>
    <ul>
      <li v-for="blog in blogList">{{blog.blo_naslov}}</li>
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
      axios.get("http://741a121.mars-e1.mars-hosting.com/api/blog")
      .then(response => {
      this.blogList = response.data.rezultat;
      });
    }
}
</script>

<style lang="css">
</style>
