<template>
  <div>

  </div>
</template>

<script>
import sweetalert from 'sweetalert'
import axios from 'axios'

export default {
  data(){
    return{
      statusLog : false,
      bookList : []
    }
  },
  methods:{
    listBook (){
      let self = this
      axios.get('http://localhost:3000/books/readbook')
      .then((value) => {
        self.bookList = value.data.data
      })
    }
  },
  created(){
    this.statusLog = localStorage.getItem('status')
    this.listBook()

  }
}
</script>

<style lang="css">
.card-footer{
  text-align: right;
}

.card-header{
  text-align: left;
}
</style>
