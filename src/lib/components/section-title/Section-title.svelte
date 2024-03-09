<script>
  import './_section-title.scss'

  export let subTitle = false;
  export let title;
  export let paragraph;
  export let button = false;
  export let secondary = false;
</script>

<div class="{secondary ? 'section-title section-title--secondary' : 'section-title'}">
  <p class="title--intro">{subTitle ? subTitle : ''}</p>
  <h2 class="title title--h2 underline">{title}</h2>
  <p class="paragraph">{paragraph}</p>
  {#if button}
    <a href="#contact">
      <button class="btn btn-primary">{button}</button>
    </a>
  {/if}
</div>
