<template>
  <div>
    <Header/>
    <HomeContent/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import HomeContent from '@/components/HomeContent.vue'

export default {
  name: 'home',
  components: {
    Header,
    Footer,
    HomeContent
  }
}
</script>
