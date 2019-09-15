<template>
  <div class="container-fluid">
    <app-progress-bar :goalCount="goals.length" :maxGoals="maxGoals"></app-progress-bar>
    <!-- Could pass as "newGoal($event)" but no need; Vue.js does it implicitly -->
    <app-new-goal @goalAdded="newGoal"></app-new-goal>
    <!-- Not relevant that deleteGoal is used in both GoalGrid and this root component; naming could be different. In this file it refers to the method defined below. Also, index is automatically passed, as content was automatically passed for @goalAdded above -->
    <app-goal-grid :goals="goals" @goalDeleted="deleteGoal"></app-goal-grid>
    <div class="row">
      <div class="col text-center">
        <div class="alert alert-info">Note: Click on a goal to delete it.</div>
      </div>
    </div>
  </div>
</template>

<!-- This is the root Vue instance/root component -->
<script>
  import GoalGrid from './components/GoalGrid.vue';
  import NewGoal from './components/NewGoal.vue';
  import ProgressBar from './components/ProgressBar.vue';

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
      },
      deleteGoal(index) {
        // Modifies existing array, removing 1 item from it at the specified index
        this.goals.splice(index, 1);
      }
    },
    components: {
      appGoalGrid: GoalGrid,
      appNewGoal: NewGoal,
      appProgressBar: ProgressBar
    }
  }
</script>

<style>
  @import "../src/styles/global.scss";
</style>
