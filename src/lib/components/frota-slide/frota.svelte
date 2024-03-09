<script>
import { truck } from '$lib/data/frota';

// Import Swiper Svelte components
import { Swiper, SwiperSlide } from 'swiper/svelte';

import { Autoplay, Navigation } from 'swiper'

//create swiper to add pagination and other interaction with swiper
let swiper;

// Import Swiper styles
import 'swiper/scss';


import './style.scss';



import Fa from 'svelte-fa/src/fa.svelte';
import { faChevronLeft, faChevronRight } from '@fortawesome/free-solid-svg-icons/index';


import SectionTitle from '../../components/section-title/Section-title.svelte';

const title = 'Nossa frota';
const paragraph = `Veja alguns dos nossos caminhões e maquínas.`;
</script>



<div class="frota">
  <div class="frota__container container">
    <SectionTitle {title} {paragraph} />

    <div class="frota__swiper">
      <Swiper
      modules={[Autoplay, Navigation]}
      spaceBetween={50}
      slidesPerView={1}
      autoplay
      navigation
      breakpoints = {
        {768: {
          slidesPerView: 2,
        }}
      }
      on:swiper={(e) => swiper = e.detail[0]}
      >
        {#each truck as {name, description, image}}
        <SwiperSlide>
          <div class="card">
            <img src="{image}" alt="" class="card__img">
            <div class="card__body">
              <h2 class="card__title title">{name}</h2>
              <p class="card__text">
                {description}
              </p>
            </div>
          </div>
        </SwiperSlide>
        {/each}
      </Swiper>
      
      <button type=button on:click={() => swiper.slidePrev()} class="frota__prev"> 
        <Fa icon={faChevronLeft} size="4x"/>
      </button>
      <button type=button on:click={() => swiper.slideNext()} class="frota__next"> 
        <Fa icon={faChevronRight} size="4x"/>
      </button>
    </div>

    <a href="/frota" class="frota__btn">
      <button class="btn btn-primary">
        veja nossa Frota completa
      </button>
    </a>
  </div>
</div>
