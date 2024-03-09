<script>
import { page } from '$app/stores';

import logo from '$lib/images/logoC.webp';
import './style.scss'


import { onMount } from 'svelte';

onMount(() => {
  let estado = 0;
	const menuHamburger = document.querySelector('#hamburger');
	
	menuHamburger.addEventListener('click', () => {
		menuHamburger.classList.toggle('open');
		
		if (estado === 0) {
			estado = 1;
			document.querySelector('.header__list').style.display = 'flex';
			document.querySelector('.header__list').addEventListener('click', () => {
				menuHamburger.classList.remove('open');
				document.querySelector('.header__list').style.display = 'none';
				estado = 0;
			})
		} else {
			estado = 0;
			document.querySelector('.header__list').style.display = 'none';
		}
	})
})
</script>


<header class="header">
	<div class="container">
		<div class="header__logo">
			<a href="/">
				<img src={logo} alt="Logo gui locacoes" />
			</a>
		</div>
		
		<nav class="header__menu" aria-label="menu site">
			<ul class="header__list" role="presentation">
				<li class="header__item" class:active={$page.url.pathname === '/'}>
					<a href="/">Home</a>
				</li>
				<li class="header__item" class:active={$page.url.pathname === '/about'}>
					<a href="/about">Sobre nós</a>
				</li>
				<li class="header__item" class:active={$page.url.pathname === '/frota'}>
					<a href="/frota">Nossa Frota</a>
				</li>
				<li class="header__item" class:active={$page.url.pathname === '/contact'}>
					<a href="/contact">Contato</a>
				</li>
			</ul>
		</nav>


		<div id="hamburger">
		  <span></span>
		  <span></span>
		  <span></span>
		</div>
		
	</div>
</header>
