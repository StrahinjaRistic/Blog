<template>
  <div id="app">
    <nav class="nav-wraper">
      <div class="container">
        <a class="brand-logo">Blog</a>
        <a class="sidenav-trigger" data-target="mobile-links">
          <i class="material-icons">menu</i>
        </a>
      <ul class="right hide-on-med-and-down">
        <li><a @click="komp = 'blog'">Prikazi Blogove</a></li>
        <li><a @click="komp = 'dodajBlog'">Dodaj Blog</a></li>
        <li><a @click="komp = 'izbrisiBlog'">Izbrisi Blog</a></li>
     </ul>
   </div>
   </nav>

   <ul class="sidenav" id="mobile-links">
     <li><a href="#" @click="komp = 'blog'">Prikazi Blogove</a></li>
     <li><a href="#" @click="komp = 'dodajBlog'">Dodaj Blog</a></li>
     <li><a href="#" @click="komp = 'izbrisiBlog'">Izbrisi Blog</a></li>
   </ul>
    <div class="container">
    <keep-alive>
      <component :is="komp">
      </component>
    </keep-alive>
    </div>

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
