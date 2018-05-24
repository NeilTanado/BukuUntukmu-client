<template>
  <div>
    <div class="container">
      <div v-for = "book in bookList">
        <div class="card flex-row flex-wrap">
            <div class="card-header border-0">
                <img img :src=book.image alt="">
            </div>
            <div class="card-block px-2">
                <h4 class="card-title"><b> Judul Buku: </b>{{ book.judul }}</h4><br>
                <h4 class="card-text"><b> Penerbit: </b>{{ book.penerbit }}</h4><br>
                <h4 class="card-text"><b> Penulis: </b>{{ book.penulis }}</h4>
            </div>
            <div class="w-100"></div>
            <div class="card-footer w-100 text-muted">
              <button type="button" class="btn btn-info" @click="toContent(book._id)">read more?</button>
            </div>
          </div>
        <br>
      </div>
    </div>
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
        console.log(value.data.data);
        self.bookList = value.data.data
      })
    },
    toContent(id){
      localStorage.setItem('bookId',id)
      this.$router.push('/content')
    }
  },
  created(){
    this.statusLog = localStorage.getItem('status')
    this.listBook()
  }
}
</script>

<style scoped>

</style>
