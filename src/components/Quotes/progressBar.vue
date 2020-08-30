<template>
  <div>
    <div class="container my-4">
      <div class="row">
        <div class="cus">
          <div
            class="customsed text-light text-center"
            :style="{'width':number+'%'}"
          >{{arr.length}}/10</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["arr"],
  data() {
    return {
      number: "0",
    };
  },
  watch: {
    arr() {
      this.number = this.arr.length * 10;
    },
  },
};
</script>
<style scoped>
.customsed {
  height: 100%;
  background-color: green;
  width: 0%;
  transition: width 1s;
}

.cus {
  width: 800px;
  height: 28px;
  background-color: gray;
  border: 1px solid black;
}
</style>