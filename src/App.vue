<template>
  <div class="container-fluid">
    <h1 class="text-center">GoalKeeper</h1>
    <div class="col-md-8 col-lg-5 mx-auto instrux">
      <p class="my-4">Add 20 goals you'd like to achieve, no matter how big or small! When you finish one, mark it as completed and add a new one to the list.</p>
    </div>
    <app-progress-bar :goalCount="goals.length" :maxGoals="maxGoals"></app-progress-bar>
    <!-- Could pass as "newGoal($event)" but no need; Vue.js does it implicitly -->
    <app-new-goal @goalAdded="newGoal"></app-new-goal>
    <!-- Not relevant that deleteGoal is used in both GoalGrid and this root component; naming could be different. In this file it refers to the method defined below. Also, index is automatically passed, as content was automatically passed for @goalAdded above -->
    <app-goal-grid :goals="goals" @goalDeleted="deleteGoal"></app-goal-grid>
    <div class="row">
      <div class="col text-center">
        <div class="alert alert-info mt-2">Note: Click on a goal to mark it as completed.</div>
      </div>
    </div>
    <h2 class="text-center" v-show="completedGoals.length > 0">Completed</h2>
    <app-completed-goal-grid :completed-goals="completedGoals"></app-completed-goal-grid>
  </div>
</template>

<!-- This is the root Vue instance/root component -->
<script>
  import GoalGrid from './components/GoalGrid.vue';
  import NewGoal from './components/NewGoal.vue';
  import ProgressBar from './components/ProgressBar.vue';
  import CompletedGoalGrid from './components/CompletedGoalGrid.vue';

  export default {
    data() {
      return {
        goals: [
          'Add some goals!'
        ],
        completedGoals: [],
        maxGoals: 20
      }
    },
    methods: {
      // Emit event from NewGoal.vue automatically passed to parent (this file); using it here
      newGoal(goal) {
        if (this.goals.length >= this.maxGoals) {
          return alert('Please delete a goal first.')
        }
        this.goals.push(goal);
      },
      deleteGoal(index) {
        // Modifies existing array, removing 1 item from it at the specified index
        this.completedGoals.push(this.goals[index]);
        this.goals.splice(index, 1);
      }
    },
    components: {
      appGoalGrid: GoalGrid,
      appNewGoal: NewGoal,
      appCompletedGoalGrid: CompletedGoalGrid,
      appProgressBar: ProgressBar
    }
  }
</script>

<style>
  @import "../src/styles/global.scss";
</style>
