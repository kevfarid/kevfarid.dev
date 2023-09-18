<script>
  import { onMount } from 'svelte';

  let windowWidth = window.innerWidth;
  let items = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]; // Tu array de datos

  // Función para dividir el array en subarrays
  function splitArray(array, chunkSize) {
    const result = [];
    for (let i = 0; i < array.length; i += chunkSize) {
      result.push(array.slice(i, i + chunkSize));
    }
    return result;
  }

  let subarrays = splitArray(items, 3); // Dividir el array en subarrays de 3 elementos

  // Actualizar la división cuando cambie el ancho de la ventana
  function handleResize() {
    windowWidth = window.innerWidth;
    subarrays = splitArray(items, windowWidth < 600 ? 1 : 3); // Cambia el tamaño de los subarrays según el ancho de la ventana
  }

  onMount(() => {
    window.addEventListener('resize', handleResize);
    return () => {
      window.removeEventListener('resize', handleResize);
    };
  });
</script>

{#each subarrays as subarray (subarrayIndex)}
  <div class="subarray">
    {#each subarray as item (itemIndex)}
      <div class="item">{item}</div>
    {/each}
  </div>
{/each}

<style>
  .subarray {
    display: flex;
  }

  .item {
    padding: 10px;
    border: 1px solid #ccc;
    margin: 5px;
  }
</style>
