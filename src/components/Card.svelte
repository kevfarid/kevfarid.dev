<script>
  export const liveUrl = undefined;
  export const repoUrl = undefined;
  export let title = '';
  export let image = '';
  export let key = -1;

  const randomHeight = (index) => {
    const heights = [320, 380, 440];
    const newIndex =
      index === -1 ? Math.floor(Math.random() * heights.length) : index;

    return heights[newIndex % heights.length];
  };
</script>

<article
  class="flex w-full border border-zinc-800 rounded-lg overflow-hidden"
  style={`height: ${randomHeight(key)}px`}
>
  <img src={image} alt={title} class="w-full h-auto object-cover" />
</article>
