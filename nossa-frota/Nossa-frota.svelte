

<script>
import './style.scss';
import Frota from '../../components/frota-slide/frota.svelte';

</script>

<section class="nossa-frota">
  <div class="container nossa-frota__container">
    <div class="nossa-frota__intro">
      <h2 class="title title--h2 underline">nossa frota</h2>
      <p>Veja alguns dos nossos caminhões e maquínas</p>
    </div>
    
    <Frota />
    <a href="/frota" class="nossa-frota__btn">
      <button class="btn btn-primary">
        veja nossa Frota completa
      </button>
    </a>
  </div>
</section>
