<template>
  <div class="row">
    <app-goal v-for="(goal, index) in goals" v-bind:key="index">{{ goal }}</app-goal>
  </div>
</template>

<script>
  import Goal from './Goal.vue';

  export default {
    props: ['goals'],
    components: {
      appGoal: Goal
    }
  }
</script>

<style>

</style>