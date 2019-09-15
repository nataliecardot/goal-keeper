<template>
  <div class="row justify-content-center">
    <!-- Native modifier instructs Vue.js to react to a click on that component if it happens on the native element of this component. So it registers the click on the app-goal component div, which is what sits in the HTML code in the end, with the native modifier, Vue.js knows that even though the click happened on the HTML code of that component, it should treat it as if it were a click on app-quote (not possible without modifier since it's not appended to the DOM) -->
    <app-goal v-for="(goal, index) in goals" v-bind:key="index" @click.native="deleteGoal(index)">{{ goal }}</app-goal>
  </div>
</template>

<script>
  import Goal from './Goal.vue';

  export default {
    props: ['goals'],
    components: {
      appGoal: Goal
    },
    methods: {
      deleteGoal(index) {
        this.$emit('goalDeleted', index);
      }
    }
  }
</script>

<style>

</style>