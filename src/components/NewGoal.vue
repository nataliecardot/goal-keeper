<template>
  <div class="row justify-content-center">
    <!-- Offsets are being used to center the textarea and button within the divs; otherwise they're flush left -->
    <form class="col-md-8 col-lg-5 col-xl-4 mt-5 mb-4">
      <div class="form-group">
        <textarea autofocus class="form-control" rows="3" v-model="goal" v-on:keyup.enter="createNew"></textarea>
      </div>
      <div class="form-group">
        <button class="btn btn-primary" :disabled="!goal" @click.prevent="createNew">Add goal</button>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        goal: null
      }
    },
    methods: {
      createNew() {
        this.$emit('goalAdded', this.goal);
        this.goal = null
      }
    }
  }
</script>

<style>

</style>