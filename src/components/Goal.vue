<template>
  <div class="col-md-6 col-lg-4 col-xl-3 mb-4">
    <div class="card">
      <div class="card-body goal">
        <!-- Slots are used to render content passed in from outside to a child component. An alternative to props; to pass in more complex/lengthy content -->
        <!-- With slots, styling is set up on child component, everything else is handled on parent component -->
        <!-- Using slot because quote content should come from outside so that the thing passing in the content is the thing deciding how it should appear. Here, only creating place it will be rendered in the end, but the thing holding the content for it should determine how it looks -->
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style>
  .card-body {
    font-size: 24px;
    color: #6e6e6e;
  }

  .goal {
    cursor: pointer;
  }

  .goal:hover {
    background-color: #ffe2e2;
  }
</style>