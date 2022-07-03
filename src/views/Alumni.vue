<template>
  <section>
    <NavbarPage :token=token />
    <div class="container-fluid pt-5 pb-5">
      <div class="container pt-5 pb-5">
        <video width="100%" height="auto" autoplay>
          <source src="../assets/infokuliah.mp4" type="video/mp4" />
        </video>
        <div class="text-center pb-2">
          <p class="section-title px-5">
            <span class="px-2">Alumni Kami</span>
          </p>
          <h1 class="mb-4">Para Alumni Kami</h1>
        </div>
        <div class="row">
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <div class="position-relative overflow-hidden mb-4" style="border-radius: 100%">
              <img class="img-fluid w-100" src="../assets/images/alumni-1.jpg" alt="" />
            </div>
            <h4>Julia Smith</h4>
            <i>Sastra Perancis - UI</i>
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <div class="position-relative overflow-hidden mb-4" style="border-radius: 100%">
              <img class="img-fluid w-100" src="../assets/images/alumni-2.jpg" alt="" />
            </div>
            <h4>Jhon Doe</h4>
            <i>Hukum - UGM</i>
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <div class="position-relative overflow-hidden mb-4" style="border-radius: 100%">
              <img class="img-fluid w-100" src="../assets/images/alumni-3.jpg" alt="" />
            </div>
            <h4>Mollie Ross</h4>
            <i>Sastra Inggris - UI</i>
          </div>
          <div class="col-md-6 col-lg-3 text-center team mb-5">
            <div class="position-relative overflow-hidden mb-4" style="border-radius: 100%">
              <img class="img-fluid w-100" src="../assets/images/alumni-4.jpg" alt="" />
            </div>
            <h4>Donald John</h4>
            <i>Hukum - UI</i>
          </div>
        </div>
      </div>
    </div>
    <FooterPage />
  </section>
</template>

<script>
import NavbarPage from '../components/Navbar.vue'
import FooterPage from '../components/Footer.vue'
export default {
  name: 'AlumniPage',
  components: {
    NavbarPage,
    FooterPage
  },
  data () {
    return {
      token: localStorage.getItem('access_token')
    }
  },
  metaInfo: {
    // if no subcomponents specify a metaInfo.title, this title will be used
    title: 'Alumni',
    // all titles will be injected into this template
    titleTemplate: '%s | Infokuliah.id'
  }
}
</script>

<style>
</style>
