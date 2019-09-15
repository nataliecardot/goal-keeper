<template>
  <div class="row">
    <div class="col">
      <h2>Goals Added</h2>
      <div class="progress">
      	<div
          class="progress-bar"
          role="progressbar"
          aria-valuenow="60"
          aria-valuemin="0"
          aria-valuemax="100"
          :style="{width: (quoteCount / maxQuotes) * 100 + '%'}"
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