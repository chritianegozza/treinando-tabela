# treinando-tabela
criando tabela e botão com saudação
![image](https://user-images.githubusercontent.com/72118415/114282423-4e64fb00-9a1a-11eb-8fb3-ba6338d8e116.png)




HTML


<!DOCTYPE html>
<html>
   
    <head>

   <title>Tabela</title>
 <link rel="stylesheet" href="css/styles.css"> 

   
    </head>
    <body>
        <p class="page-subtitle">
            Loja Super Amigos 
        </p> 

        <h1>Tabela</h1>
        <div id="root"></div>
        <script src="js/script.js"></script> 
    </body>
    

    <p><h3>Vamos aprender um botão</h3></p>
    <button onclick="delayedAlert();">Compre aqui. </button>
    <p></p>
    </html>

   
   
   
   CSS
   
   table {
    border: 2px solid #000;
    padding-left: initial;
    text-align: center;
    display: inline-block;
    margin: 0 auto;

}

table tr td{
    background-color:rgba(206, 71, 194, 0.856);
    text-align: center;
    color:white;
width: 70%;
}


h1{
    background-color: rgba(206, 71, 194, 0.856);
    text-align: center;
    color: white;
}


h3 {
    display: block;
    margin: 0 auto;
    background-color: rgba(206, 71, 194, 0.856);
    text-align: center;
    color: white;
} 

body{
    font-family: 'Roboto Mono',monospace;
    text-align:center;
    background-image: url('https://image.freepik.com/free-photo/pink-white-rose-with-petal_1339-1165.jpg');
    background-color: #000000;
    background-size: cover;
    background-position: center top;
    background-repeat: no-repeat;
  }
  
  
  .page-subtitle {
    color: rgba(206, 71, 194, 0.856);
    margin: 0 0 5px; 
    font-weight: 900;
  }

   button {
    border: 0;
    color: #ffffff;
    background: #da1eca;
    font-weight:bold;
    padding: 10px 15px;
    font-size: 12px;
    margin-top: 15px;
    cursor: pointer;
    transition: .1s;
  }

   button:hover {
    opacity:.8;
  }
  
  
  js
  
  const root = document.querySelector("#root");

//JSON - JavaScript Object Notayion
const produtos =  [
    {  itens: "Blusa", preço:  21 },
    {  itens: "Saia", preço:  22 },
    {  itens: "Sapato", preço: 15  },]

function createBody() {
     const newProdutos = produtos.map(function (produto) {
    return `<tr>
    <td>${produto.itens}</td>
    <td>${produto.preço}</td>
    </tr>`;
});

return newProdutos; 
}    

const tableBody = createBody(); 

const table = `<table>
  <tr>
    <td>Itens</td>
    <td>Preço</td>
  </tr>    
  ${tableBody.join("")}
</table>`;

root.insertAdjacentHTML("beforeend", table);


var timeoutID;

function delayedAlert() {
  timeoutID = window.setTimeout(window.alert, 1*100, 'Volte sempre e aproveite suas compras!');
}
