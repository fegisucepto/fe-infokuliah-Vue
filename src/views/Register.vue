<template>
<section class="vh-100 bg-image"
  style="background-image: url('https://mdbcdn.b-cdn.net/img/Photos/new-templates/search-box/img4.webp');">
  <div class="mask d-flex align-items-center h-100 gradient-custom-3">
    <div class="container h-100">
      <div class="row d-flex justify-content-center align-items-center h-100">
        <div class="col-12 col-md-9 col-lg-7 col-xl-6">
          <div class="card" style="border-radius: 15px;">
            <div class="card-body p-5">
              <h2 class="text-uppercase text-center mb-5">Create an account</h2>

              <form @submit.prevent="submit">
                <div class="form-outline mb-4">
                  <input type="email" class="form-control form-control-lg" v-model="email" placeholder="Email"/>
                  <label class="form-label" for="form3Example3cg">Your Email</label>
                </div>

                <div class="form-outline mb-4">
                  <input type="password" class="form-control form-control-lg" v-model="password" placeholder="password"/>
                  <label class="form-label" for="form3Example4cg">Password</label>
                </div>

                <div class="form-check d-flex justify-content-center mb-5">
                  <input class="form-check-input me-2" type="checkbox" value="" id="form2Example3cg" />
                  <label class="form-check-label" for="form2Example3g">
                    I agree all statements in <a href="#!" class="text-body"><u>Terms of service</u></a>
                  </label>
                </div>

                <div class="d-flex justify-content-center">
                  <button type="submit"
                    class="btn btn-primary px-4">Register</button>
                </div>

                <p class="text-center text-muted mt-5 mb-0">Have already an account? <a href="/login"
                    class="fw-bold text-body"><u>Login here</u></a></p>

              </form>

            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<script>
import server from '@/api'
export default {
  name: 'RegisterPage',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async submit () {
      await server.post('/register', {
        email: this.email,
        password: this.password
      })
      this.$router.push('/login')
    }
  },
  beforeCreate () {
    const token = localStorage.getItem('access_token')
    if (token) {
      this.$router.push('/home')
    }
  }
}
</script>

<style></style>
