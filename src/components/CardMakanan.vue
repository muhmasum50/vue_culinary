<template>
  <div class="card card-makanan">
    <img :src=" 'assets/produk/' +jajanan.gambar" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{jajanan.nama}}</h5>
      <p class="card-text">
        Harga Rp. {{jajanan.harga}}
      </p>
      <a href="#" class="btn btn-primary"><b-icon-cart></b-icon-cart> Pesan</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardMakanan",
  props: ["jajanan"],
};
</script>

<style>
</style>