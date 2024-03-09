<script>
import { truck, categories } from '$lib/data/frota';

let selected = 'todos';

const filterSelection = (e) => {
  selected = e.target.dataset.name;
};

import './style.scss';

</script>



<div class="b-frota">
  <div class="container">

    <h2 class="title title--h2 b-frota__title">Confira nossos caminhoes</h2>

    <div class="b-frota__categories">
      {#each categories as category}
        <button class="b-frota__btn" 
                class:active={selected === category}
                data-name={category}
                on:click={filterSelection}> 
          {category}
        </button>
      {/each}
    </div>

    <div class="b-frota__grid">
    {#each truck as {name, description, image, category}}
      {#if selected === 'todos'}
        <div class="card card__show" data-name={category}>
          <img src="{image}" alt="" class="card__img">
          <div class="card__body">
            <h2 class="card__title title">{name}</h2>
            <p class="card__text">
              {description}
            </p>
          </div>
        </div>
        
      {:else}

        <div class="card" data-name={category} class:card__show={category === selected}>
          <img src="{image}" alt="" class="card__img">
          <div class="card__body">
            <h2 class="card__title title">{name}</h2>
            <p class="card__text">
              {description}
            </p>
          </div>
        </div>
      {/if}
  {/each}

      
    </div>

  </div>
</div>
