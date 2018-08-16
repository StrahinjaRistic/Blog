<template>
  <div id="app">
    <button @click="komp = 'blog'">Prikazi Blogove</button>
    <button @click="komp = 'dodajBlog'">Dodaj Blog</button>
    <button @click="komp = 'izbrisiBlog'">Izbrisi Blog</button>
    <keep-alive>
      <component :is="komp">
      </component>
    </keep-alive>
  </div>
</template>

<script>
import Blog from './Blog.vue'
import DodajBlog from './DodajBlog.vue'
import IzbrisiBlog from './IzbrisiBlog.vue'
export default {
  data:function(){
    return{
      komp : 'blog'
    }
  },
  components:{
    blog : Blog,
    dodajBlog : DodajBlog,
    izbrisiBlog : IzbrisiBlog
  }
}
</script>

<style>
</style>
