<template>
  <div>
    <form class="container">
      <div class="form-group">
        <label>Judul Buku</label>
        <input type="text" v-model="judul" class="form-control" placeholder="your book title?">
      </div>
      <div class="form-group">
        <label>Penerbit</label>
        <input type="text" v-model="penerbit" class="form-control" placeholder="nama penerbitnya??">
      </div>
      <div class="form-group">
        <label>Penulis</label>
        <input type="text" v-model="penulis" class="form-control" placeholder="nama penulisnya??">
      </div>
      <div class="form-group">
        <label>description</label>
        <textarea class="form-control" rows="5" placeholder="write the description here" v-model="question"></textarea>
      </div>
      <div class="form-group">
        <input type="file" @change="fileName" required>
      </div>
      <button type="button" class="btn btn-outline-info" @click="createBook()">Submit Ulasanmu</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'
import sweetalert from 'sweetalert'

export default {
  data(){
    return{
      penerbit:'',
      penulis:'',
      judul:'',
      description:'',
      file: null,
    }
  },
  methods:{
    fileName (event) {
      this.file = event.target.files[0]
    },
    createBook () {
    if(this.penerbit === '' || this.penulis === '' || this.judul === '' || this.description === ''){
      swal("Oppppsss!", "harap isi content!", "error");
    }else{
      let tokenToSent = localStorage.getItem('token')
      let formData = new FormData()
      formData.append('penerbit', this.penerbit)
      formData.append('penulis', this.penulis)
      formData.append('judul', this.judul)
      formData.append('description', this.description)
      formData.append('image', this.file)
      axios.post('http://localhost:3000/books/createbook', formData,{
        headers:{
          'token':tokenToSent
        }
      })
        .then(response => {
          swal("Good job!", "You give review to book!", "success");
          this.$router.push('/')
        })
        .catch(err => {
          console.log(err)
        })
      }
    },
  }
}
</script>

<style lang="css">
.shadow-textarea textarea.form-control::placeholder {
    font-weight: 300;
}
.shadow-textarea textarea.form-control {
    padding-left: 0.8rem;
}

</style>
