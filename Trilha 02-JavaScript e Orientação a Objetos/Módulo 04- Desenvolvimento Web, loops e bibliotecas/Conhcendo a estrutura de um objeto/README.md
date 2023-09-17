# Instruções:

Crie um código com um objeto chamado **"Banco"**. Ele deverá ter propriedades que incluem conta, saldo, tipo de conta e agência e os seus métodos devem ser: buscar saldo, depósito, saque e número da conta. 
observações:
- **busca saldo** deve retornar o valor atual do saldo;
- para o **deposito** , você deverá passar um valor como parâmetro e adicioná-lo no saldo final do objeto; 
- para o **saque** , você deverá passar um valor como parâmetro e adicioná-lo no saldo final do objeto; 
- o **numero da conta**  deve retornar o número da conta.

# RESPOSTA

## CÓDIGO EM JS
```JS
const Banco = {
  conta: "12345-6",
  saldo: 1000.00,
  tipoConta: "Corrente",
  agencia: "7890",

  buscarSaldo: function() {
    return this.saldo;
  },

  deposito: function(valor) {
    if (valor > 0) {
      this.saldo += valor;
      return `Depósito de R$ ${valor} realizado com sucesso. Novo saldo: R$ ${this.saldo}`;
    } else {
      return "Valor inválido para depósito.";
    }
  },

  saque: function(valor) {
    if (valor > 0 && valor <= this.saldo) {
      this.saldo -= valor;
      return `Saque de R$ ${valor} realizado com sucesso. Novo saldo: R$ ${this.saldo}`;
    } else if (valor <= 0) {
      return "Valor inválido para saque.";
    } else {
      return "Saldo insuficiente para realizar o saque.";
    }
  },


  numeroConta: function() {
    return this.conta;
  }
};

console.log("Número da Conta:", Banco.numeroConta());
console.log("Saldo Atual:", Banco.buscarSaldo());
console.log(Banco.deposito(500.00));
console.log(Banco.saque(200.00));

```

