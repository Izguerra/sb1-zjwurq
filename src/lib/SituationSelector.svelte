<script>
  import { createEventDispatcher } from 'svelte';
  import { situations } from './situations.js';
  
  const dispatch = createEventDispatcher();
  let selectedSituation = null;
  
  function handleSelect(situation) {
    selectedSituation = situation;
    dispatch('select', situation);
  }
</script>

<div class="list-group mb-4">
  {#each situations as situation}
    <button
      type="button"
      class="list-group-item list-group-item-action {selectedSituation === situation ? 'active' : ''}"
      on:click={() => handleSelect(situation)}
    >
      {situation.negative}
    </button>
  {/each}
</div>