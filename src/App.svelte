<script>
  import 'bootstrap/dist/css/bootstrap.min.css';
  import SituationSelector from './lib/SituationSelector.svelte';
  import ResponseDisplay from './lib/ResponseDisplay.svelte';
  
  let selectedSituation = null;
  let showResponse = false;
  
  function handleSituationSelect(event) {
    selectedSituation = event.detail;
    showResponse = false;
  }
  
  function handleFlip() {
    showResponse = true;
  }
</script>

<main class="container py-4">
  <div class="row justify-content-center">
    <div class="col-md-8">
      <div class="card">
        <div class="card-body">
          <h1 class="card-title text-center mb-4">SalesResponse</h1>
          <h5 class="card-subtitle mb-3 text-muted text-center">Select a situation to get a mood-lifting response!</h5>
          
          <SituationSelector on:select={handleSituationSelect} />
          
          <div class="d-grid gap-2">
            <button
              class="btn btn-primary btn-lg"
              disabled={!selectedSituation}
              on:click={handleFlip}
            >
              Flip It! 🔄
            </button>
          </div>
          
          <ResponseDisplay situation={selectedSituation} {showResponse} />
        </div>
      </div>
    </div>
  </div>
</main>

<style>
  :global(body) {
    background-color: #f8f9fa;
  }
</style>