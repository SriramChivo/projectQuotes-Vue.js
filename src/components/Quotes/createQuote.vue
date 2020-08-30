<template>
  <div id="app">
    <div class="container my-4">
      <div class="row">
        <div class="offset-md-3 col-md-6">
          <div class="form-group">
            <label for="exampleFormControlTextarea1">Create New Quote</label>
            <textarea
              class="form-control"
              id="exampleFormControlTextarea1"
              rows="3"
              ref="quoteCreate"
            ></textarea>
            <button @click="create" class="btn btn-primary btn-sm text-uppercase my-2">Create</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  props: ["arr"],
  methods: {
    create() {
      console.log(this.$refs.quoteCreate.value);
      console.log("created");
      console.log(this.arr.length - 1);
      if (this.arr.length + 1 <= 10) {
        this.$emit("created", this.$refs.quoteCreate.value);
        this.$refs.quoteCreate.value = "";
      } else {
        alert("Maximum is 10 quotes we can add");
      }
    },
  },
};
</script>

<style>
</style>
