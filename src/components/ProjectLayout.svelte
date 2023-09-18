<script type="ts">
  import lang from '../constants/lang';

  import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
  import Card from './Card.svelte';

  const projects = lang.projects;
</script>

<Splide
  aria-label="My Favorite Images"
  options={{
    perPage: 3,
    focus: 0,
    omitEnd: true,
    gap: 16,
    autoplay: true,
    rewind: true,
    type: 'loop',
    width: '300',
    breakpoints: {
      640: {
        perPage: 1,
      },
      1280: {
        perPage: 2,
      },
    },
  }}
  hasTrack={false}
  class="py-8"
>
  <SplideTrack>
    {#each projects as project}
      <SplideSlide>
        <Card {...project} liveUrl={project.liveUrl} />
      </SplideSlide>
    {/each}
  </SplideTrack>
  <div class="splide__arrows select-none">
    <button class="splide__arrow splide__arrow--prev"
      ><i class="fa-solid fa-angle-left text-black" /></button
    >
    <button class="splide__arrow splide__arrow--next"
      ><i class="fa-solid fa-angle-right text-black" /></button
    >
  </div>
</Splide>

<style>
  @import '@splidejs/svelte-splide/css';
</style>
