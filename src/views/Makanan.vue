<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-3">
        <div class="col">
          <h2>Daftar <strong>Makanan</strong></h2>
        </div>
      </div>

      <div class="row mt-3">
        <div class="col">
          <div class="input-group mb-2">
            <input
              v-model="cari"
              type="text"
              class="form-control"
              placeholder="Cari Makanan Kesukaanmu"
              @keyup="cariMakanan"
            />
            <div class="input-group-prepend">
              <div class="input-group-text">
                <b-icon icon="search"></b-icon>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-md-4 mt-4" v-for="jajanan in makanan" :key="jajanan.id">
          <CardMakanan :jajanan="jajanan" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from "@/components/Navbar.vue";
  import CardMakanan from "@/components/CardMakanan.vue";
  import axios from "axios";

  export default {
    name: "Makanan",
    components: {
      Navbar,
      CardMakanan,
    },
    data() {
      return {
        makanan: [],
        cari: '',
        info: null,
        loading: true,
        errored: false,
      };
    },
    methods: {
      setMakanan(data) {
        this.makanan = data;
      },
      cariMakanan() {
        axios
        .get("http://localhost:3000/products?q="+this.cari)
        .then((response) => this.setMakanan(response.data))
        .catch((error) => console.log(error));
      }
    },
    mounted() {
      axios
        .get("http://localhost:3000/products")
        .then((response) => this.setMakanan(response.data))
        .catch((error) => console.log(error));
    },
  };
</script>