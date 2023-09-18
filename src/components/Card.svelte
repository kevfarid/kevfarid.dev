<script>
  export let liveUrl = '';
  export let title = '';
  export let image = '';

  import lang from '../constants/lang';
</script>

<article
  class="flex w-full border border-zinc-800 rounded-lg overflow-hidden relative aspect-video group"
>
  {#if liveUrl}
    <a
      href={liveUrl}
      class="absolute h-full w-full cursor-pointer top-0 left-0 z-30"
      target="_blank"
    >
      <span class="hidden">{lang.projectsTexts.live}</span>
    </a>
  {/if}
  <div
    class="absolute from-black/70 to-transparent bottom-0 left-0 h-20 bg-gradient-to-t z-20 flex justify-between items-end w-full px-4 pb-2"
  >
    <h2 class="w-full text-lg font-semibold">{title}</h2>
  </div>
  <img
    src={image}
    alt={title}
    class="w-full h-auto object-cover object-top relative z-0 group-hover:scale-110 transition-transform delay-300 ease-linear"
  />
</article>
