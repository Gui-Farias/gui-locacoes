<script>
  import logo from '$lib/images/logo.webp'
  import Form from '../../components/form/form.svelte';
  import './style.scss'
  
  </script>
  
  <section class="contact" id="contact">
    <div class="contact__container container">
      <div class="contact__content">
        <img src="{logo}" alt="" width="350">
      </div>
      <Form />
    </div>
  </section>
  