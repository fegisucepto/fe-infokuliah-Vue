<template>
  <div>
    <img class="card-img-top mb-2" :src="data.imageURL" alt="" />
    <div class="card-body text-center">
      <h4 class="card-title">{{ data.name }}</h4>
      <p class="card-text">
        {{ data.description }}
      </p>
      <p class="text-dark font-weight-bold">Rp.{{ data.price }}</p>
      <div class="buttons mb-1 mt-1">
        <a href="/courses/buy/" class="btn btn-warning px-4 mr-2">
          Beli Kursus
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CorsesPage',
  props: ['data']
}
</script>

<style></style>
