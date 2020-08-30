<template>
  <div class="cuscss p-5" @click="deleted" style="cursor:pointer" :class="{custom:hov}">
    {{quote}}
    <!--<div class="row text-center my-2">
      <div
        v-for="(quotes,ind) in quote"
        :key="quotes"
        class="cust col-md-3 border border-dark my-2 p-5"
      >
        <p @click="delete">{{ind}}{{quotes}}</p>
      </div>
    </div>-->
  </div>
</template>

<script>
export default {
  data() {
    return {
      hov: false,
    };
  },
  props: ["quote", "ind"],
  methods: {
    deleted() {
      console.log("deleted");
      console.log(this.ind);
      this.$emit("deleted", this.ind);
    },
    hovered() {
      console.log("hover");
      if (this.hov == true) {
        this.hov = false;
      } else {
        this.hov = true;
      }
    },
  },
};
</script>

<style scoped>
.custom {
  background-color: pink;
}
.cuscss {
  font-family: cursive;
}
.cuscss:hover {
  background-color: pink;
}
</style>
