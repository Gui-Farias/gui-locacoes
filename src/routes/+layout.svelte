<script>
import Footer from '../lib/components/footer/Footer.svelte';
import Header from '../lib/components/header/Header.svelte';
import BtnWpp from '../lib/components/btn-wpp/btn-wpp.svelte'
import './style.scss';


</script>

<Header />

<div class="app">

  <main>

	<slot />
  
  </main>
</div>
<BtnWpp />
<Footer />

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
	}
</style>
