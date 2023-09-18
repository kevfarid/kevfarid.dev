<script type="ts">
  import Card from './Card.svelte';
  import lang from '../constants/lang';
  import Test from './Test.svelte';

  const projects = lang.projects;
</script>

<ul class="flex gap-4">
  {#each projects as project}
    <Card {...project} />
  {/each}
  <Test />
</ul>
