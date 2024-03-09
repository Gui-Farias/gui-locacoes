<script>
import './style.scss';

import SectionTitle from '../../components/section-title/Section-title.svelte';
import Composition from '../../components/composition/Composition.svelte';

const subTitle = 'Nossos serviços';
const title = 'VEICULOS & EQUIPAMENTOS';
const paragraph = 'Somos uma empresa especializada em alugar caminhões e maquinas para obras e construções, sem burocracia e com agilidade na entrega: você escolhe o modelo e a gente entrega em qualquer lugar do Brasil. E pronto, é só dirigir.';
const button = 'Alugue agora'
</script>

<section class="servico">
  <div class="servico__container container">
    <SectionTitle {subTitle} {title} {paragraph} {button}/>

    <Composition />
  </div>
</section>
