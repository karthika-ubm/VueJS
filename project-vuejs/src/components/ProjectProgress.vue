<template>
  <div class="col-xl-12">
    <div class="card proj-progress-card">
      <div class="card-block">
        <div class="row">
          <div v-for="(item, index) in projectProgressSummary" :key="index" class="col-xl-3 col-md-6">
            <h6>{{ item.title }}</h6>
            <h5 class="m-b-30 f-w-700">
              {{ item.value }}
              <span :class="[getColorClass(item.percentage), 'm-l-10']">{{ item.percentage }}</span>
            </h5>
            <div class="progress">
              <div :class="getProgressBarClass(item.title)" :style="{ width: item.width }"
></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
// Import the JSON data
import projectProgressData from '../assets/jsons/Project_Progress_Summary.json';

export default {
  data() {
    return {
      projectProgressSummary: projectProgressData.project_progress_summary
    };
  },
 methods: {
    getColorClass(percentage) {
      return percentage.startsWith("+") ? "text-c-green" : "text-c-red";
    },
    getProgressBarClass(title) {
      if (title === "Published Project") {
        return "progress-bar bg-c-red";
      } else if (title === "Completed Task") {
        return "progress-bar bg-c-blue";
      } else if (title === "Successful Task") {
        return "progress-bar bg-c-green";
      } else if (title === "Ongoing Project") {
        return "progress-bar bg-c-yellow";
      } else {
        return "progress-bar bg-c-default";
      }
    }
  },

};
</script>
