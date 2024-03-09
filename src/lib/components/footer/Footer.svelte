<script>
import './style.scss'


import Fa from 'svelte-fa/src/fa.svelte';
import { faInstagram, faWhatsapp } from '@fortawesome/free-brands-svg-icons/index';
import { faEnvelope } from '@fortawesome/free-regular-svg-icons/index';


const dataAtual = new Date();
const anoAtual = dataAtual. getFullYear();
</script>


<footer class="footer">
  <div class="container footer__container">
    <div class="footer__intro">
      <p>gui Locacoes é uma empresa de locação de equipamentos para construção, infraestrutura, aterramento, entre outros </p>
      <ul class="footer__social" role="presentation">
        <li>
          <a href="#" target="_blank" rel="noopener noreferrer" aria-label="link email gui">
            <Fa icon={faEnvelope} size="2x"/>
          </a>
        </li>
        <li>
          <a href="#" target="_blank" rel="noopener noreferrer" aria-label="link instagram gui">
            <Fa icon={faInstagram} size="2x"/>
          </a>
        </li>
        <li>
          <a href="#" target="_blank" rel="noopener noreferrer" aria-label="link Whatsapp gui">
            <Fa icon={faWhatsapp} size="2x"/>
          </a>
        </li>
      </ul>
    </div>
    <div class="footer__help">
      <h2>Busca um caminhao?</h2>
      <ol>
        <li>Obras</li>
        <li>Asfalto</li>
        <li>Aterramento</li>
        <li>Linhas de transmição</li>
      </ol>
    </div>
    <nav class="footer__menu">
      <h2>gui Locaçoes</h2>
      <ul>
        <li >
					<a href="/">Home</a>
				</li>
				<li >
					<a href="/about">Sobre nós</a>
				</li>
				<li >
					<a href="/frota">Nossa frota</a>
				</li>
				<li >
					<a href="/contact">Contato</a>
				</li>
      </ul>
    </nav>
  </div>

  <div class="copyright">
    <p>© Copyright - Direitos reservados {anoAtual}</p>
  </div>
</footer>
