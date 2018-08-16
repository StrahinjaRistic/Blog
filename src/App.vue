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
     <li><a @click="komp = 'blog'">Prikazi Blogove</a></li>
     <li><a @click="komp = 'dodajBlog'">Dodaj Blog</a></li>
     <li><a @click="komp = 'izbrisiBlog'">Izbrisi Blog</a></li>
   </ul>

    <keep-alive>
      <div class="container">
      <component :is="komp">
      </component>
    </div>
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
