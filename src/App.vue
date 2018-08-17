<template>
  <div id="app">
    <header>
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
 </header>
   <main>
    <div class="container">
    <keep-alive>
      <component :is="komp">
      </component>
    </keep-alive>
    </div>
  </main>
    <footer class="page-footer">
      <div class="container">
        <div class="row">
          <div class="col l6 s12">
            <h5 class="white-text">Blog</h5>
          </div>
          <div class="col l4 offset-l2 s12">
            <ul>
              <li><a class="grey-text text-lighten-3" href="#" @click="komp = 'blog'">Prikazi Blogove</a></li>
              <li><a class="grey-text text-lighten-3" href="#" @click="komp = 'dodajBlog'">Dodaj Blog</a></li>
              <li><a class="grey-text text-lighten-3" href="#" @click="komp = 'izbrisiBlog'">Izbrisi Blog</a></li>
            </ul>
          </div>
        </div>
      </div>
      <div class="footer-copyright">
        <div class="container">
          © 2014 Copyright Text
          <a class="grey-text text-lighten-4 right">Strahinja i Boris</a>
        </div>
      </div>
    </footer>
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
