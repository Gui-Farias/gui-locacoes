<script>
	import Contact from "../../lib/block/contact/Contact.svelte";
	import Cta from "../../lib/block/cta/Cta.svelte";
  import Faq from "../../lib/block/faq/Faq.svelte";
import HeroPage from "../../lib/components/heroPage/HeroPage.svelte";
  
  const pageTitle = 'Contato'
  </script>
  
  
  <HeroPage {pageTitle}/>
  <Faq />
  <Cta />
  <Contact />
