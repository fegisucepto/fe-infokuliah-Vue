<template>
  <section>
    <NavbarPage :token=token />
    <Heroes />
    <div class="container-fluid bg-light pt-5 pb-5">
      <div class="container pt-5 pb-5 px-4 px-lg-5 h-100">
        <div class="text-center pb-2">
          <h2 class="text-dark font-weight-bold">
            Bimbingan Belajar Online Persiapan UTBK Terbaik di Indonesia!
          </h2>
          <hr class="divider" />
          <p class="card-text">
            Infokuliah.id telah meluluskan lebih dari 101.924 siswa ke PTN sejak
            tahun 1990. Soal diktat dan tryout terjamin kualitasnya dan selalu
            disesuaikan dengan soal UTBK terbaru. Dengan metode pembelajaran
            ditekankan pada konsep dan skill bernalar.
          </p>
          <p class="card-text">
            Infokuliah.id membantu siswa mencari dan membandingkan informasi
            perguruan tinggi di seluruh Indonesia supaya bisa meraih impian
            lewat kampus idaman dan jurusan yang sesuai dengan passion.
          </p>
        </div>
      </div>
    </div>

    <div class="container-fluid pt-5">
      <div class="container pt-5 pb-5">
        <div class="text-center pb-2">
          <p class="section-title px-5">
            <span class="px-2">Gabung Sekarang</span>
          </p>
          <h2 class="text-dark font-weight-bold mb-4">
            Masuk PTN Favorit Kamu
          </h2>
        </div>
        <div class="row">
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <img
              class="img-fluid w-100"
              src="http://pk4l.ugm.ac.id/wp-content/uploads/sites/51/2017/09/logo-ugm-986x1024.png"
              alt=""
            />
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <img
              class="img-fluid w-100"
              src="https://1.bp.blogspot.com/-IOm2dGW3gkc/X2gh3MuOqoI/AAAAAAAAHKA/EdK1C7LyZWE7qxQNQDPIBXFGCXH4c7U7ACLcBGAsYHQ/s1000/Logo%2BUniversitas%2BIndonesia-01.png"
              alt=""
            />
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <img
              class="img-fluid w-100"
              src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Bogor_Agricultural_University_%28IPB%29_symbol.svg/2048px-Bogor_Agricultural_University_%28IPB%29_symbol.svg.png"
              alt=""
            />
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <img
              class="img-fluid w-100"
              src="https://ditsti.itb.ac.id/wp-content/uploads/2020/09/logo_itb_1024.png"
              alt=""
            />
          </div>
        </div>
      </div>
    </div>
    <Classes />
    <FooterPage />
  </section>
</template>

<script>
import NavbarPage from '@/components/Navbar'
import FooterPage from '@/components/Footer'
import Heroes from '@/components/Heroes.vue'
import Classes from '@/components/Classes.vue'
import server from '@/api'

export default {
  name: 'HomeView',
  data () {
    return {
      token: localStorage.getItem('access_token')
    }
  },
  async created () {
    await server.get('/courses', {
      headers: {
        Authorization:
          'Bearer ' + localStorage.getItem('access_token')
      }
    })
  },
  components: {
    NavbarPage,
    FooterPage,
    Heroes,
    Classes
  },
  metaInfo: {
    // if no subcomponents specify a metaInfo.title, this title will be used
    title: 'Dashboard',
    // all titles will be injected into this template
    titleTemplate: '%s | Infokuliah.id'
  }
}
</script>
<style></style>
