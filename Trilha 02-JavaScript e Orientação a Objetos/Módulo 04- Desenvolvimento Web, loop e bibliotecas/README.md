# Instruções:

Crie um programa que contenha os seguintes tipos de funções: 
1. uma função tradicional com a palavra reservada “Function” e sem nenhum parâmetro; 
2. uma função tradicional com parâmetros e um retorno de valor; 
3. uma arrow function com parâmetros e que retorne um valor. 

Crie um programa que utilize essas três funções de forma lógica, por exemplo: um programa de calculadora. 

# RESPOSTA

## CÓDIGO EM JS:
  ```JS
//função com nenhum parametro

function nenhumParametro (){

    var mensagem= "Olá";

    return mensagem;

}

console.log(nenhumParametro());

// função com parâmetro

function parabens(nome){

    var x = ("Parabens" +" "+ nome)

    return x;

}

var nome= "Maria"

console.log(parabens(nome))

// função arrow

const frase = (nome) => {console.log("Olá, "+""+ nome+","+" tudo bem?")};

var x= "Maria"
console.log(frase(x))

```

