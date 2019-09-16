<template>
  <div class="row justify-content-center">
    <app-completed-goal v-for="(completedGoal, index) in completedGoals" v-bind:key="index">{{ completedGoal }}</app-completed-goal>
  </div>
</template>

<script>
  import CompletedGoal from './CompletedGoal.vue';

  export default {
    props: ['completedGoals'],
    components: {
      appCompletedGoal: CompletedGoal
    }
  }
</script>

<style>

</style>