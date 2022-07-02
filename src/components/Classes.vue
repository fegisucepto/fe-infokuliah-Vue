<template>
  <div class="container-fluid pt-5 pb-5 bg-light">
    <div class="container pt-5 pb-5">
      <div class="text-center pb-2">
        <p class="section-title px-5">
          <span class="px-2">Program Kami</span>
        </p>
        <h2 class="mb-4">Program Unggulan InfoKuliah.ID</h2>
      </div>
      <div class="row">
        <div class="col-lg-4 mb-5">
          <div class="card border-0 bg-light shadow-sm pb-2">
            <img
              class="card-img-top mb-2"
              src="../assets/images/program-stan.png"
              alt=""
            />
            <div class="card-body text-center">
              <h4 class="card-title">Program Garansi STAN</h4>
              <p class="card-text">
                Program Garansi STAN/Kedinasan dengan sistem pembelajaran privat
                maupun group class. Siswa belajar dengan kondisi professional,
                fokus terhadap tujuan dan pengajar pendamping yang kompeten
                untuk persiapan ujian masuk STAN.
              </p>
            </div>
          </div>
        </div>
        <div class="col-lg-4 mb-5">
          <div class="card border-0 bg-light shadow-sm pb-2">
            <img
              class="card-img-top mb-2"
              src="../assets/images/program-soshum.png"
              alt=""
            />
            <div class="card-body text-center">
              <h4 class="card-title">Program UTBK Soshum</h4>
              <p class="card-text">
                Program Garansi STAN/Kedinasan dengan sistem pembelajaran privat
                maupun group class. Siswa belajar dengan kondisi professional,
                fokus terhadap tujuan dan pengajar pendamping yang kompeten
                untuk persiapan ujian masuk STAN.
              </p>
            </div>
          </div>
        </div>
        <div class="col-lg-4 mb-5">
          <div class="card border-0 bg-light shadow-sm pb-2">
            <img
              class="card-img-top mb-2"
              src="../assets/images/program-ptn.png"
              alt=""
            />
            <div class="card-body text-center">
              <h4 class="card-title">Program Masuk PTN</h4>
              <p class="card-text">
                Program Garansi STAN/Kedinasan dengan sistem pembelajaran privat
                maupun group class. Siswa belajar dengan kondisi professional,
                fokus terhadap tujuan dan pengajar pendamping yang kompeten
                untuk persiapan ujian masuk STAN.
              </p>
            </div>
          </div>
        </div>
      </div>
      <a v-if="!token" href="/Couses" class="btn btn-warning mt-1 py-3 px-5"
        >Program Lainnya</a
      >
      <a
        v-else
        href="/Couses"
        class="btn btn-warning mt-1 py-3 px-5"
        role="button"
        >Program Lainnya</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: 'ClassesSection',
  props: ['token']
}
</script>

<style></style>
