<template>
  <section>
    <div class="container all m-4">
      <div class="form m-5">
        <div class="register">
          <p>Add News</p>
        </div>
        <div class="row">
          <div class="col">
            <form action="/news/<%= data[0].id %>" method="POST">
              <div class="input-group mb-3">
                <input
                  type="text"
                  class="form-control"
                  name="name"
                  placeholder="Name"
                  aria-describedby="basic-addon1"
                  value=""
                />
              </div>
              <div class="input-group mb-3">
                <input
                  type="text'"
                  class="form-control"
                  name="imageURL"
                  placeholder="imageURL"
                  aria-describedby="basic-addon1"
                  value=""
                />
              </div>
              <div class="input-group mb-3">
                <textarea
                  name="description"
                  id="description"
                  cols="80"
                  rows="10"
                ></textarea>
              </div>
              <div class="input-group mb-3">
                <input
                  type="text"
                  class="form-control"
                  name="Catagory"
                  placeholder="Catagory"
                  aria-describedby="basic-addon1"
                  value=""
                />
              </div>
            </form>
          </div>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AddPage'
}
</script>

<style></style>
