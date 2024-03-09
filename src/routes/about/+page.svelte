<script>
	import About from "../../lib/block/about/About.svelte";
	import Cta from "../../lib/block/cta/Cta.svelte";
	import Faq from "../../lib/block/faq/Faq.svelte";
import HeroPage from "../../lib/components/heroPage/HeroPage.svelte";

const pageTitle = 'Sobre nós'
</script>


<HeroPage {pageTitle}/>
<About />
<Cta />
<Faq />
