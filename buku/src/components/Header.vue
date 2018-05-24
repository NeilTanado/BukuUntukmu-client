<template>
  <nav class="navbar navbar-expand-lg navbar-light mb-4" style="background-color: #e3f2fd">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
      <a class="navbar-brand" href="#">Buku Untukmu™</a>
      <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
        <li class="nav-item active">
          <a class="nav-link" @click="toHome()">Home <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" href="#">Share</a>
        </li>
      </ul>
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit" @click="toCreateBook()">Buat Ulasan</button>
        <button class="btn btn-outline-secondary my-2 my-sm-0 ml-3" @click="toLogin()">Login</button>
    </div>
  </nav>
</template>

<script>
import LoginView from '@/components/LoginView.vue'

export default {
  components:{
    LoginView
  },
  data(){
    return{

    }
  },
  methods:{
    toLogin:function(){
      this.$router.push('/login')
    },
    toHome:function(){
      this.$router.push('/')
    },
    toCreateBook:function(){
      this.$router.push('/book')
    }
  }

}
</script>

<style>
</style>
