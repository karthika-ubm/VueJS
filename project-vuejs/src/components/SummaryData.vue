<!-- Summary.vue -->
<template>
  <div class="col-md-12 col-xl-4">
    <div v-for="(item, index) in summary" :key="index" class="card comp-card">
      <div class="card-body">
        <div class="row align-items-center">
          <div class="col">
            <h6 class="m-b-25">{{ item.title }}</h6>
            <h3 class="f-w-700">{{ item.value }}</h3>
            <p class="m-b-0">{{ item.duration }}</p>
          </div>
          <div class="col-auto">
            <i :class="item.iconClass"></i>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// Import the JSON data
import summaryData from '../assets/jsons/summary.json';

export default {
  data() {
    return {
      summary: summaryData.summary
    };
  },
  mounted() {
    // Log the summary data
    console.log('Summary Data:', this.summary);
  }
};
</script>
