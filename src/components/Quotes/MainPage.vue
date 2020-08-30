<template>
  <div id="app">
    <!-- {{arr}} -->
    <div class="row">
      <div class="col-md-6 offset-md-3">
        <progress-bar :arr="arr"></progress-bar>
      </div>
    </div>
    <create-quotes :arr="arr" @created="arr.unshift($event)"></create-quotes>
    <template>
      <div class="container">
        <div class="row mx-3">
          <div
            class="col-md-4 col-lg-3 border border-dark my-1"
            v-for="(quotes,ind) in arr"
            :key="quotes"
          >
            <div class="panel panel-default">
              <show-quotes :quote="quotes" :ind="ind" @deleted="arr.splice($event, 1);"></show-quotes>
            </div>
          </div>
        </div>
      </div>
      <div class="row my-4">
        <div class="col-md-6 offset-md-3 bg-warning">Note: Click on quotes to delete the Quote</div>
      </div>
    </template>
  </div>
</template>

<script>
import create from "./createQuote.vue";
import show from "./ShowQuotes.vue";
import progress from "./progressBar.vue";

export default {
  data() {
    return {
      arr: [],
    };
  },
  components: {
    createQuotes: create,
    showQuotes: show,
    progressBar: progress,
  },
};
</script>

<style>
</style>
