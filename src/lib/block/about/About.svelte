<script>
import logo from '$lib/images/logo.webp'

import SectionTitle from '../../components/section-title/Section-title.svelte';
import './style.scss';


const subTitle = 'Sobre nós';
const title = 'gui LOCAÇÕES';
const paragraph = `A gui locações, está no mercado há 6 anos, prestando serviços na área
                  de alguel de Máquinas Pesadas e Caminhões por todo o Brasil.
                  Buscando qualidade em relação aos serviços prestados, focando a prioridade 
                  com segurança de nossos colaboradores e patrimônios movimentados.
                  Oferecemos consultoria gratuita junto ao cliente antes de iniciar uma operação.`;
const button = 'CONHEÇA MAIS'
</script>

<section class="about">
  <div class="container about__container">
    <SectionTitle {subTitle} {title} {paragraph} {button} secondary/>

    <div class="about__img">
      <img src={logo} alt="">
    </div>
  </div>
</section>
