<template>
  <div>
    <Header/>
    <CreateBook/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import CreateBook from '@/components/CreateBook.vue'


export default {
  name: 'home',
  components: {
    Header,
    Footer,
    CreateBook
  }
}
</script>
