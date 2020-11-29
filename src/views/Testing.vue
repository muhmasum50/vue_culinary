<template>
  <div>
    <Navbar />
     <div class="container">
      <div class="row mt-3">
        <div class="col">
          <h2>Find <strong>Movie</strong></h2>
        </div>
      </div>

      <div class="row mt-3">
        <div class="col">
          <div class="input-group mb-2">
            <input
              v-model="cari"
              type="text"
              class="form-control"
              placeholder="Cari Movie Kesukaanmu"
              @keyup="cariMovie"
            />
            <div class="input-group-prepend">
              <div class="input-group-text">
                <b-icon icon="search"></b-icon>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row mb-4" style="height:50px">
        <div class="col-md-4 mt-4" v-for="film in movie" :key="film.imdbID">
          <div class="card card-makanan">
            <img :src="film.Poster" class="card-img-top" alt="..." />
            <div class="card-body">
              <h5 class="card-title">{{film.Title}}</h5>
              <p class="card-text">
                Tahun : {{film.Year}}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import axios from "axios"

export default {
  name: "Testing",
  components: {
    Navbar,
  },
  data() {
    return {
      movie: [],
      cari : '',
      info: null,
      loading: true,
      errored: false,
    };
  },
  methods:{
    setMovie(data) {
      this.movie = data
    },
    cariMovie() {
      axios
        .get("http://www.omdbapi.com/?apikey=3e33beff&s="+this.cari)
        .then((response) => this.setMovie(response.data.Search))
        .catch((error) => console.log(error));
    }
  },
  mounted(){
    axios.get("http://www.omdbapi.com/?apikey=3e33beff&s=avengers")
        .then((response) => this.setMovie(response.data.Search))
        .catch((error) => console.log(error));
  }
};
</script>

<style>
</style>