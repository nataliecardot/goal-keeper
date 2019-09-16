<template>
  <div class="row justify-content-center">
    <div class="col-md-6">
      <h3>Added</h3>
      <div class="progress">
      	<div
          class="progress-bar bg-secondary"
          role="progressbar"
          aria-valuenow="60"
          aria-valuemin="0"
          aria-valuemax="100"
          :style="{width: (goalCount / maxGoals) * 100 + '%'}"
        >
          {{ goalCount }} / {{ maxGoals }}
      	</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['goalCount', 'maxGoals']
  }
</script>