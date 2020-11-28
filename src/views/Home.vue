<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Header />
      <div class="row">
        <div class="col">
          <h2>Badokan <strong>Terbaik</strong></h2>
        </div>
        <div class="col">
          <router-link to="/makanan" class="btn btn-primary float-right"
            >Lihat Semua</router-link
          >
        </div>
      </div>

      <div class="row mb-3">
        <div class="col-md-4 mt-4" v-for="jajanan in makanan" :key="jajanan.id">
          <CardMakanan :jajanan="jajanan"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Header from "@/components/Header.vue";
import CardMakanan from "@/components/CardMakanan.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Navbar,
    Header,
    CardMakanan,
  },
  data() {
    return {
      makanan: [],
    };
  },
  methods: {
    setMakanan(data) {
      this.makanan = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => this.setMakanan(response.data))
      .catch((error) => console.log(error))
  },
};
</script>
