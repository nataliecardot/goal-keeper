<template>
  <div class="container">
    <app-goal-grid :goals="goals"></app-goal-grid>
  </div>
</template>

<!-- This is the root Vue instance/root component -->
<script>
  import GoalGrid from './components/GoalGrid.vue';

  export default {
    data() {
      return {
        goals: [
          'Add some goals!'
        ],
        maxGoals: 15
      }
    },
    components: {
      appGoalGrid: GoalGrid
    }
  }
</script>

<style>
  @import "../src/styles/global.scss";
</style>
