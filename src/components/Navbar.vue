<template>
  <div class="container-fluid bg-light position-relative shadow">
    <nav
      class="navbar navbar-expand-lg bg-light navbar-light py-3 py-lg-0 px-0 px-lg-5"
      id="mainNav"
    >
      <div class="container px-4 px-lg-5">
        <a class="navbar-brand font-weight-bold text-secondary" href="/"
          ><img src="../assets/Infokuliah.png" alt="Infokuliah.id"
        /></a>
        <button
          type="button"
          class="navbar-toggler"
          data-toggle="collapse"
          data-target="#navbarCollapse"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="collapse navbar-collapse justify-content-between"
          id="navbarResponsive"
        >
          <div class="navbar-nav font-weight-bold mx-auto py-0">
            <ul class="navbar-nav ms-auto my-2 my-lg-0">
              <li class="nav-item">
                <a class="nav-link active" href="/">Home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="/Couses">Paket Kursus</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="/alumni">Alumni</a>
              </li>
            </ul>
          </div>
          <a
            v-if="!token"
            class="btn btn-warning px-4 mr-2"
            href="/register"
            role="button"
            >Register</a
          >
          <a
            v-if="!token"
            class="btn btn-primary px-4"
            href="/login"
            role="button"
            >Login</a
          >
          <a
            v-else
            class="btn btn-primary px-4"
            v-on:click="logout"
            href="/login"
            role="button"
            >Logout</a
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'NavbarPage',
  props: ['token'],
  methods: {
    logout () {
      localStorage.clear()
      this.$router.push('/login')
    }
  }
}
</script>

<style></style>
