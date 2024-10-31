<script>
  export let situation = null;
  export let showResponse = false;
</script>

{#if situation && showResponse}
  <div class="alert alert-success mt-4" role="alert">
    <h4 class="alert-heading">Here's your positive spin! 🌟</h4>
    <p class="mb-0">{situation.positive}</p>
  </div>
{/if}