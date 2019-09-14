<template>
  <div class="row justify-content-center">
    <!-- Offsets are being used to center the textarea and button within the divs; otherwise they're flush left -->
    <form class="col-md-8 col-lg-6">
      <div class="form-group">
        <label for="goal">Goal</label>
        <textarea id="goal" class="form-control" rows="3" v-model="goal"></textarea>
      </div>
      <div class="form-group">
        <button class="btn btn-primary" @click.prevent="createNew">Add goal</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        goal: ''
      }
    },
    methods: {
      createNew() {
        this.$emit('goalAdded', this.goal);
        this.goal = ''
      }
    }
  }
</script>

<style>

</style>