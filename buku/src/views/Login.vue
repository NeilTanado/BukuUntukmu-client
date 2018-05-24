<template>
  <div>
    <Header/>
    <LoginView/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import LoginView from '@/components/LoginView.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Header,
    LoginView,
    Footer
  }
}
</script>

<style scoped>
  .footer{
    position: absolute;
    bottom: 0;
    background-color: #e3f2fd;
  }
</style>
