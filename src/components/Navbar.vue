<template>
  <b-navbar toggleable="lg" type="light">
    <div class="container">
      <b-navbar-brand href="#">App</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <router-link class="nav-link" to="/">Home</router-link>
          <router-link class="nav-link" to="/makanan">Makanan</router-link>
          <router-link class="nav-link" to="/movie">Movie</router-link>
        </b-navbar-nav>

        <b-navbar-nav class="ml-auto">
          <router-link class="nav-link" to="/keranjang"
            >Keranjang
            <b-icon-cart></b-icon-cart>
            <span class="badge badge-primary ml-2">0</span>
          </router-link>
        </b-navbar-nav>
      </b-collapse>
    </div>
  </b-navbar>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style>
</style>