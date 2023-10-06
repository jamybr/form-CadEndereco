# Índice 

[Formulário de Cadastro de Endereço]()  
[Descrição](#descri%C3%A7%C3%A3o)  
[Instruções de Uso](#instru%C3%A7%C3%B5es-de-uso)  
[Funcionalidades](#funcionalidades)    
[Composição do Projeto](#%EF%B8%8Fcomposi%C3%A7%C3%A3o-do-projeto)   
[Funções em Javascript](#fun%C3%A7%C3%B5es-em-javascript)  
[Funções em Index.html](#fun%C3%A7%C3%B5es-em-indexhtml)  
[Funções em Javascript](#fun%C3%A7%C3%B5es-em-javascript)  
[Tecnologias Utilizadas](#tecnologias-utilizadas)  
[Fontes consultadas](#fontes-consultadas)  
[Colaboradores](#colaboradores)  
[Autores](#autores)  

# Formulário de Cadastro de Endereço

<img src="imgs/entrar.gif">

# 📌Formulário de Cadastro de Endereço

 ## 📝Descrição

 * Este é um projeto simples de cadastro de endereço que permite consultar facilmente informações de domicílio por meio de uma interface as informações de endereço a partir de um CEP (código postal) fornecido.

 ## 👾Instruções de Uso

 * Abra o arquivo 'index.html' em um navegador web;
 * Preencha os campos do formulário com as informações de endereço desejadas;
 * Clique no botão "Entrar" para enviar o formulário.

 ## 🔛Funcionalidades  

  ### 1. Cadastro de Endereço:  
  * O formulário permite aos usuários inserirem as seguintes informações de endereço:  
   
  * Rua    
  * Número  
  * Bairro  
  * Complemento (opcional)  
  * Cidade  
  * Estado  

  ### 2. Consulta Automática de CEP:  

  * Quando o usuário insere um CEP válido no campo correspondente, o sistema automaticamente realiza uma consulta à API ViaCEP para obter e preencher os campos de rua, bairro, cidade e estado.  

  ### 3. Estilização Responsiva:  

  * O projeto possui estilos CSS que garantem uma boa aparência e usabilidade tanto em dispositivos desktop quanto em dispositivos móveis.  

 ## ⚙️Composição do Projeto  

 * `index.html` : Contém a estrutura HTML do formulário de cadastro de endereço.  
 * `main.css` : Arquivo de estilo para personalizações adicionais.  
 * `controller.js` : Script JavaScript para lidar com a consulta de CEP e preenchimento automático dos campos de endereço.  

## Funções em Javascript

     const limparFormulario = (endereco) => {
     document.getElementById('rua').value = '';
     document.getElementById('bairro').value = '';
     document.getElementById('cidade').value = '';
     document.getElementById('estado').value = '';
     }  

     const eNumero = (numero) => /^[0-9]+$/.test(numero); 
     const cepValido = (cep) => cep.length == 8 && eNumero(cep);

    const preencherForumulario = (endereco) => {
    document.getElementById('rua').value = endereco.logradouro;
    document.getElementById('bairro').value = endereco.bairro;
    document.getElementById('cidade').value = endereco.localidade;
    document.getElementById('estado').value = endereco.uf;

    const pesquisarCep = async() => {
    limparFormulario();
    const url = `https://viacep.com.br/ws/${cep.value}/json/`;  

    if(cepValido(cep.value)){
        const dados = await fetch(url); 
        const addres = await dados.json(); 
        
        if(addres.hasOwnProperty('erro')){ 
            alert('CEP não encontrado!');
        }else {
            preencherForumulario(addres);
        }
    }else{
        alert('CEP incorreto!');
    } 
    }  

 ## Funções em Index.html  

    <body>
    <form method="get" action=".">
      <div class="container">
      <h1>Cadastro de Endereço</h1>        
        </div>
    <div class="col-md-2">
      <label for="inputZip" class="form-label">CEP</label>
      <input type="text" class="form-control" id="cep">
      </div><br><br>
      <div class="row">
      <div class="form-group col-md-4">
          <label for="rua">Rua</label>
          <input type="text" class="form-control" id="rua" placeholder="Rua dos Bestas">
      </div>
      <div class="form-group col-md-2">
        <label for="inputAddress">N.º</label>
        <input type="text" class="form-control" id="numero" placeholder="nº 0">
    </div>
    <div class="form-group col-md-4">
      <label for="inputAddress2">Bairro</label>
      <input type="text" class="form-control" id="bairro">
      </div>
    </div><br><br>
    <div class="row">
      <div class="form-group col-md-3">
          <label for="complemento">Complemento</label>
          <input type="text" class="form-control" id="complemento" placeholder="Apartamento, hotel, casa, etc.">
      </div>
      <div class="form-group col-md-4">
          <label for="cidade">Cidade</label>
          <input type="text" class="form-control" id="cidade">
      </div>
      <div class="form-group col-md-3">
          <label for="estado">Estado</label>
          <input type="text" class="form-control" id="estado">
      </div>
    </div>
    <br><br>
      <button class="btn btn-primary" onclick="">Entrar</button>
    </div>
    </form>
    
    <script type="text/javascript" src="./controller.js"></script>
    </body>
    
    </html>

 
 ## ⌨️Tecnologias Utilizadas

 * Css  
 * HTML  
 * GitHub  
 * Javacript  
 * BootStrap (versão 5.3.1)  

 ## 📑Fontes consultadas

 ## 🤝🏻🤝🏻Colaboradores

 * [Professor Leonardo Rocha](https://github.com/LeonardoRochaMarista)
 * [Leonardo Rocha](https://github.com/LeonardoRochaMarista)
 * [Witória Beatriz](https://github.com/Witoriabeatriz)

 ## ✒️Autores
 * Esse projeto foi criado por [Jasminy Matias e Silva](https://github.com/jamybr)

