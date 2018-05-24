<template>
  <div>
    <div class="card flex-row flex-wrap">
        <div class="card-header border-0">
            <img img :src=image alt="">
        </div>
        <div class="card-block px-2">
            <h4 class="card-title"><b> Author: </b>{{ owner }}</h4><br>
            <h4 class="card-title"><b> Judul Buku: </b>{{ judul }}</h4><br>
            <h4 class="card-text"><b> Penerbit: </b>{{ penerbit }}</h4><br>
            <h4 class="card-text"><b> Penulis: </b>{{ penulis }}</h4>
        </div>
        <div class="w-100"></div>
      </div>
      <form class="container mt-5">
        <div class="form-group">
          <label>Your Answer Here</label>
          <textarea class="form-control" rows="5" placeholder="write the answer here.." v-model="answer"></textarea>
        </div>
        <button type="button" class="btn btn-outline-success" @click="submitAnswer()">Submit Answer</button>
      </form>
  </div>
</template>

<script>
import axios from 'axios'
import sweetalert from 'sweetalert'

export default {
  data(){
    return{
      bookId: '',
      comment : [],
      penerbit:'',
      penulis:'',
      owner:'',
      judul:'',
      image:'',
      newcomment : '',
    }
  },
  methods:{
    submitAnswer(){

    }
  },
  created(){
    this.bookId = localStorage.getItem('bookId')
    axios.post('http://localhost:3000/books/onebook',{id : this.bookId})
    .then((value) => {
      console.log(value.data.value);
      this.penulis = value.data.value.penulis
      this.judul = value.data.value.judul
      this.penerbit = value.data.value.penerbit
      this.image = value.data.value.image
      this.owner = value.data.value.owner.name
    })
    .catch((err) => {
      console.log(err);
    })
  }
}
</script>

<style lang="css">
  .buttonright{
    text-align: right
  }
</style>
