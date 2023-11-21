
# PERGUNTA

Crie uma fábrica de veículos utilizando o padrão Prototype com base no exemplo apresentado no Hipertexto 2. Os requisitos do projeto devem ser:


- implemente uma classe abstrata Veículo com um construtor padrão e os métodos clone e represent; 
- o construtor da classe Veículo deve receber modelo, marca, cor e numeroRodas como parâmetros; 
- crie pelo menos duas subclasses da classe Veículo, que acrescentem um ou mais atributos, por exemplo: carro que tem dois campos a mais, como numeroRodas e numeroPortas; 
- desenvolva uma classe Aplicação que deve criar um array com seis veículos com dois tipos de veículos diferentes (subclasses), utilizando o método clone dos objetos para preencher o array; 
- na classe Aplicação, implemente um método que retorne um array com o mesmo tamanho do array de veículos, onde cada elemento deve ser um clone dos elementos do array veículos; 
- no final, deve imprimir na tela o retorno da função represent de cada elemento desse novo array de clones de veículos.

## CÓDIGO EM JAVASCRIPT


```JS
// Classe abstrata Veículo
class Veiculo {
  constructor(modelo, marca, cor, numeroRodas) {
    this.modelo = modelo;
    this.marca = marca;
    this.cor = cor;
    this.numeroRodas = numeroRodas;
  }

  clone() {
    // Método clone abstrato
    throw new Error("Método clone deve ser implementado nas subclasses");
  }

  represent() {
    // Método represent para exibir informações do veículo
    console.log(`Modelo: ${this.modelo}, Marca: ${this.marca}, Cor: ${this.cor}, Número de Rodas: ${this.numeroRodas}`);
  }
}

// Subclasse Carro
class Carro extends Veiculo {
  constructor(modelo, marca, cor, numeroRodas, numeroPortas) {
    super(modelo, marca, cor, numeroRodas);
    this.numeroPortas = numeroPortas;
  }

  clone() {
    return new Carro(this.modelo, this.marca, this.cor, this.numeroRodas, this.numeroPortas);
  }
}

// Subclasse Moto
class Moto extends Veiculo {
  constructor(modelo, marca, cor, numeroRodas, cilindradas) {
    super(modelo, marca, cor, numeroRodas);
    this.cilindradas = cilindradas;
  }

  clone() {
    return new Moto(this.modelo, this.marca, this.cor, this.numeroRodas, this.cilindradas);
  }
}

// Classe Aplicação
class Aplicacao {
  static criarVeiculos() {
    const veiculos = [];

    const carro1 = new Carro("Civic", "Honda", "Preto", 4, 4);
    const carro2 = new Carro("Fusca", "Volkswagen", "Azul", 4, 2);
    const moto1 = new Moto("CBR500R", "Honda", "Vermelho", 2, 500);
    const moto2 = new Moto("YZF-R6", "Yamaha", "Branco", 2, 600);

    veiculos.push(carro1, carro2, moto1, moto2);

    return veiculos;
  }

  static clonarVeiculos(veiculos) {
    return veiculos.map((veiculo) => veiculo.clone());
  }

  static imprimirRepresentacao(veiculos) {
    veiculos.forEach((veiculo) => veiculo.represent());
  }
}

// Uso da Aplicação
const veiculosOriginais = Aplicacao.criarVeiculos();
const veiculosClonados = Aplicacao.clonarVeiculos(veiculosOriginais);

console.log("Representação dos Veículos Originais:");
Aplicacao.imprimirRepresentacao(veiculosOriginais);

console.log("\nRepresentação dos Veículos Clonados:");
Aplicacao.imprimirRepresentacao(veiculosClonados);
```
