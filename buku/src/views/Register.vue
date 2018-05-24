<template>
  <div>
    <Header/>
    <RegisterView/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import RegisterView from '@/components/RegisterView.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Header,
    RegisterView,
    Footer
  }
}
</script>

<style>
</style>
