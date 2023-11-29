# Instruções: 
Considerando a solução apresentada no Hipertexto 5, aplique o padrão de projeto Strategy para criar uma simples calculadora. Os requisitos para avaliar o projeto são:

implementar uma interface Strategy com o método abstrato execute() . Deve haver três classes concretas que implementam a Strategy para realizar as operações de Soma , Subtração e Multiplicação de números inteiros;
o método execute() deve receber dois números inteiros como parâmetros e retornar o resultado também como número inteiro;
como input do usuário, a aplicação deve receber o primeiro valor, depois o segundo e, por último, a operação matemática que deve realizar;
no final, a aplicação deve definir qual Strategy será usada, com base na operação informada, e imprimir o resultado da operação.

## Código em Typescript:
```JS

// Interface 
interface OperacaoStrategy {
    execute(a: number, b: number): number;
}

class SomaStrategy implements OperacaoStrategy {
    execute(a: number, b: number): number {
        return a + b;
    }
}

class SubtracaoStrategy implements OperacaoStrategy {
    execute(a: number, b: number): number {
        return a - b;
    }
}

class MultiplicacaoStrategy implements OperacaoStrategy {
    execute(a: number, b: number): number {
        return a * b;
    }
}
class Calculadora {
    private operacao: OperacaoStrategy | null = null;

    setOperacao(operacao: OperacaoStrategy): void {
        this.operacao = operacao;
    }

    executarOperacao(a: number, b: number): void {
        if (this.operacao) {
            const resultado = this.operacao.execute(a, b);
            console.log(`Resultado da operação: ${resultado}`);
        } else {
            console.log("Por favor, defina a operação antes de executar.");
        }
    }
}

const calculadora = new Calculadora();

const valor1 = parseInt(prompt("Digite o primeiro valor: ") || "0", 10);
const valor2 = parseInt(prompt("Digite o segundo valor: ") || "0", 10);

const operacaoSelecionada = prompt("Digite a operação (+, -, *): ");

switch (operacaoSelecionada) {
    case '+':
        calculadora.setOperacao(new SomaStrategy());
        break;
    case '-':
        calculadora.setOperacao(new SubtracaoStrategy());
        break;
    case '*':
        calculadora.setOperacao(new MultiplicacaoStrategy());
        break;
    default:
        console.log("Operação inválida.");
}

calculadora.executarOperacao(valor1, valor2);


```
