<template>
  <div class="container-fluid">
    <!-- Could pass as "newGoal($event)" but no need; Vue.js does it implicitly -->
    <app-new-goal @goalAdded="newGoal"></app-new-goal>
    <app-goal-grid :goals="goals"></app-goal-grid>
  </div>
</template>

<!-- This is the root Vue instance/root component -->
<script>
  import GoalGrid from './components/GoalGrid.vue';
  import NewGoal from './components/NewGoal.vue';

  export default {
    data() {
      return {
        goals: [
          'Add some goals!'
        ],
        maxGoals: 15
      }
    },
    methods: {
      // Emit event from NewGoal.vue automatically passed to parent (this file); using it here
      newGoal(goal) {
        this.goals.push(goal);
      }
    },
    components: {
      appGoalGrid: GoalGrid,
      appNewGoal: NewGoal
    }
  }
</script>

<style>
  @import "../src/styles/global.scss";
</style>
