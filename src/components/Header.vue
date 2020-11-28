<template>
  <div class="header">

    <!-- web -->
    <div class="d-none d-md-block">
        <div class="row mt-4">
        <div class="col-md-6">
            <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
                <h2>
                <strong>Menu Enak Cuma Ada Disini ....</strong><br />Buruan
                Cobain,
                </h2>
                <p>Ayo segera pilih dan pesan makanan favorit kamu</p>
                <router-link to="/makanan" class="btn btn-primary btn-lg">
                <b-icon-arrow-right></b-icon-arrow-right>
                <span> Pesan disini ...</span>
                </router-link>
            </div>
            </div>
        </div>
        <div class="col-md-6">
            <img src="../assets/gambar/burger.png" width="100%" alt="" />
        </div>
        </div>
    </div>

    <!-- mobile -->
    <div class="d-sm-block d-md-none">
        <div class="row mt-4">
            <div class="col-md-6 mb-4">
                <img src="../assets/gambar/burger.png" width="100%" alt="" />
            </div>
            <div class="col-md-6">
                <div class="d-flex h-100">
                <div class="justify-content-center align-self-center">
                    <h2>
                    <strong>Menu Enak Cuma Ada Disini ....</strong><br />Buruan
                    Cobain,
                    </h2>
                    <p>Ayo segera pilih dan pesan makanan favorit kamu</p>
                    <router-link to="/makanan" class="btn btn-primary btn-lg">
                    <b-icon-arrow-right></b-icon-arrow-right>
                    <span> Pesan disini ...</span>
                    </router-link>
                </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
</style>