<template>
  <div>
    <Header/>
    <ContentBook/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import ContentBook from '@/components/ContentBook.vue'

export default {
  name: 'bookContent',
  components: {
    Header,
    Footer,
    ContentBook
  }
}
</script>
