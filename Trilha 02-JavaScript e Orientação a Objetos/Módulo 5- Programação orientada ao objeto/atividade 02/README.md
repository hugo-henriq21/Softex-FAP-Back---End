# Instruções
Utilizando a linguagem JavaScript, crie uma situação matemática na qual os números precisam ser informados pelo usuário. Além disso, deve ocorrer uma exceção dentro do código. Utilize os métodos try(), catch() e finally() para realizar a captura e o tratamento dessa exceção.

## Código em JS
``` JS
try{
  var x= parseFloat(prompt("Insira um valor um denominador para a divisão por 10 "));
  
  if(x==0||isNaN(x)){
   console.log("O denominador não pode ser zero")
  }
  
  var y= parseFloat(prompt("Insira um numero para a raiz quadrada"));

  if(y<0 || isNaN(y)){
    console.log("Os números negativos não pertencem ao domínio das raízes")
  }
  
  var divisao= 10/x;
  var radiciacao= Math.sqrt(y)
  
} catch (error){
  console.log(error.messasge)
}finally{
  console.log(divisao)
  console.log(radiciacao)
}
```
