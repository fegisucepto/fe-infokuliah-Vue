<template>
  <section>
    <div>
      <Navbar :token=token />
      <!-- <div>
        <nav
          class="navbar navbar-expand-lg navbar-light sticky-top py-3 bg-light mb-3"
          id="mainNav"
        >
          <div class="container px-4 px-lg-5">
            <a class="navbar-brand" href="/home"
              ><img src="../assets/Infokuliah.png" alt="Infokuliah.id"
            /></a>
            <button
              class="navbar-toggler navbar-toggler-right"
              type="button"
              data-bs-toggle="collapse"
              data-bs-target="#navbarResponsive"
              aria-controls="navbarResponsive"
              aria-expanded="false"
              aria-label="Toggle navigation"
            >
              <span class="navbar-toggler-icon"> </span>
            </button>
            <div class="collapse navbar-collapse" id="navbarResponsive">
              <ul class="navbar-nav ms-auto my-2 my-lg-0">
                <li class="nav-item">
                  <a class="nav-link active" href="/Couses">My Kursus</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link active" href="/alumni">Alumni</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="/">Log Out</a>
                </li>
              </ul>
            </div>
          </div>
        </nav>
      </div> -->

      <div class="container-fluid pt-5 pb-5">
        <div class="container pt-5 pb-5">
          <div class="row">
            <div class="col-lg-12 mb-5">
              <div class="card border-0 shadow-sm pb-2">
                <Couses
                  v-for="courses in Couses"
                  :key="courses.id"
                  :data="courses"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
      <FooterPage />
    </div>
  </section>
</template>

<script>
import server from '@/api'
import FooterPage from '@/components/Footer'
import Couses from '@/components/Couses'
import Navbar from '../components/Navbar.vue'

export default {
  name: 'CousesPage',
  components: {
    FooterPage,
    Couses,
    Navbar
  },
  data () {
    return {
      Couses: [],
      token: localStorage.getItem('access_token')
    }
  },
  created () {
    this.getCouses()
  },
  methods: {
    getCouses () {
      server
        .get('/courses', {
          headers: {
            Authorization: 'Bearer ' + localStorage.getItem('access_token')
          }
        })
        .then(({ data }) => {
          this.Couses = data.data
        })
        .catch((err) => {
          console.log(err)
        })
    }
  },
  beforeCreate () {
    const token = localStorage.getItem('access_token')
    if (!token) {
      this.$router.push('/login')
    }
  }
}
</script>

<style></style>
