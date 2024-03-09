<script>
import './_faq.scss'

import jQuery from "jquery"

import { onMount } from 'svelte';

onMount(() => {
  var accordionButtons = jQuery('.accordion-controls li button');
  
  const answers = document.querySelectorAll('.faq__answer')
  jQuery(answers).css('display', 'none');
  document.querySelector('#content-1').style.display = "block";
  
  function accordionToggle() {
    jQuery('.accordion-controls li button').on('click', function(e) {
      var jQuerycontrol = jQuery(this);
      checkOthers(jQuerycontrol[0]);
      
      var accordionContent = jQuerycontrol.attr('aria-controls');
      
      var isAriaExp = jQuerycontrol.attr('aria-expanded');
      var newAriaExp = (isAriaExp == "false") ? "true" : "false";

      if (jQuerycontrol[0].ariaExpanded != 'true') {
        jQuerycontrol.attr('aria-expanded', newAriaExp);
        
        var isAriaHid = jQuery('#' + accordionContent).attr('aria-hidden');
        if (isAriaHid == "true") {
          jQuery('#' + accordionContent).attr('aria-hidden', "false");
          jQuery('#' + accordionContent).css('display', 'block');
        } else {
          jQuery('#' + accordionContent).attr('aria-hidden', "true");
          jQuery('#' + accordionContent).css('display', 'none');
        }
      }
    });
  };

  function checkOthers(elem) {
    for (var i=0; i<accordionButtons.length; i++) {
      if (accordionButtons[i] != elem) {
        if((accordionButtons[i]).ariaExpanded == 'true') {
          accordionButtons[i].setAttribute('aria-expanded', 'false');
          var content = jQuery(accordionButtons[i]).attr('aria-controls');
          document.querySelector(`#${content}`).setAttribute('aria-hidden', 'true');
          document.querySelector(`#${content}`).style.display = 'none';
        }
      }
    } 
  };
  //call this function on page load
  accordionToggle();
  // ...
});


let items = [
  {'question':'Você entrega em todo Brasil?', 'answer': 'Sim, entregamos em todo Brasil, é só você escolher o seu modelo ou entrar em contato para nos te ajudar e assim que nos falarmos já envio o caminhao para o lugar desejado.'},
  {'question':'Tem muita burocracia para alugar ?', 'answer': 'Nao, fazemos todo o processo rapido e regulamentado.'},
  {'question':'Quero um caminhao, mas nao sei qual', 'answer': 'Isso é normal, termos diversos modelos e certamente um deles vai te atender bem, entre em contato que nos te ajudaremos a escolher o melhor.'},
  {'question':'Voces tambem vendem?', 'answer': 'Nao, apenas alugamos por tempo de contrato, acabando o contrato tem a possibilidade de renovacao.'},
  {'question':'Se o caminhao furar o pneu?', 'answer': 'Todo dano que o caminhao sofrer natural, nos cobrimos, nesse caso só levar o caminhao na oficina e nos reembolsamos o valor.'},
  {'question':'Demais dúvidas:', 'answer': 'Me mande um whatsapp ou e-mail.'},
];

</script>

<section class="faq" id="faq">
  <div class="container faq__container">
    <div class="faq__list">

      <h2 class="title title--h2 faq__title">POR QUE NOS ESCOLHER ?</h2>
      <ul aria-label="FAQ Accordion Control Group Buttons" class="accordion-controls">
        {#each items as item, i}
        <li class="faq__item">
          <button aria-controls="content-{i+1}" aria-expanded="{i+1 === 1 ? "true" : false}" id="accordion-control-{i+1}" class="faq__question">{item.question}</button>
          <div aria-hidden="true" id="content-{i+1}" class="faq__answer">
            <p>{item.answer}</p>
          </div>
        </li>
        {/each}
        
      </ul>
    </div>
  </div>
</section>
