<script>
  import './_form.scss'
    
  function sendEmail() {
    console.log('oi')
  }
  
  function email() {
    if (document.querySelector('#name').value.length < 3) {
      alert( "Preencha campo NOME COMPLETO!" );
      document.querySelector('#name').focus();
      return false;
    } else if (document.querySelector('#tel').value.length < 8) {
      alert( "Preencha campo TELEFONE com um numero valido!" );
      document.querySelector('#tel').focus();
      return false;
    } else if ( 
      document.querySelector('#email').value == "" ||
      document.querySelector('#email').value.indexOf('@') == -1 ||
      document.querySelector('#email').value.indexOf('.')==-1 
    ){
      alert( "Preencha campo E-MAIL corretamente!" );
      document.querySelector('#email').focus();
      return false;
    } else if (document.querySelector('#term') === false) {
      return false;
    }
    else {
      sendEmail();
    }
  }
  
  </script>
  
  <form action="" method="post" class="form">
    <div class="form__group">
      <label for="name" required>  Nome completo*
        <input type="text" name="name" id="name">
      </label>

      <label for="tel" required>Telefone*
        <input type="text" name="tel" id="tel" maxlength="15">
      </label>
    </div>
  
    <div class="form__group">
      <label for="email" required>Email*
        <input type="email" name="email" id="email">
      </label>
    </div>
  
    <div class="form__group">
      <label for="service">Serviço*
        <select name="service" id="service">
          <option value="saude">Caçambas</option>
          <option value="profissional">Veículos</option>
          <option value="pessoal">Caminhões</option>
          <option value="somatizacoes">Terraplanagem</option>
          <option value="ansiedade">Módulos habitacionais </option>
        </select>
      </label>
    </div>
  
    <div class="form__group">
      <label for="date">Quando
        <input type="date" name="date" id="date">
      </label>
    </div>

    <div class="form__group">
      <label for="term" class="form__aceite" required>
        <input type="checkbox" name="term" id="term">Eu autorizo o envio dessas informaçoes*
      </label>
    </div>
  
    <button class="btn btn-primary" on:click|preventDefault={email}> Agende uma conversa </button>
  </form>
  