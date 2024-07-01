<script>
    export let component;
  </script>
  
  <style>
    .showcase-container {
      width: 100px;
      height: 100px;
      border: 1px solid #000000;
      background-color: white;
      padding: 10px;
      margin: 10px;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 500px;
    }
  </style>
  
  <div class="showcase-container">
    {#if component}
      <svelte:component this={component} />
    {/if}
  </div>
  