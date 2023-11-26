# Instruções
Aplique o padrão de projeto decorator para criar um sanduíche de frango assado com pepperoni e queijo mussarela ralado. O projeto deve seguir os seguintes critérios:

- deve imprimir no console: Sanduíche de Carne, Bacon, QueijoMussarelaRalado custa $7,49.
- o sanduíche de frango assado custa $4,50.
- o ingrediente adicional pepperoni custa $0,99.
- o ingrediente adicional queijo mussarela ralado custa $2,00.
- crie as classes necessárias: FrangoAssado, Pepperoni e QueijoMussarelaRalado.

## Código em TypeScript
``` JS
interface Sanduiche {
  descricao(): string;
  custo(): number;
}

class SanduicheBasico implements Sanduiche {
  descricao(): string {
    return "Sanduíche";
  }

  custo(): number {
    return 4.5;
  }
}

abstract class AdicionalDecorator implements Sanduiche {
  protected sanduiche: Sanduiche;

  constructor(sanduiche: Sanduiche) {
    this.sanduiche = sanduiche;
  }

  abstract descricao(): string;
  abstract custo(): number;
}

class FrangoAssado extends AdicionalDecorator {
  constructor(sanduiche: Sanduiche) {
    super(sanduiche);
  }

  descricao(): string {
    return this.sanduiche.descricao() + ", Frango Assado";
  }

  custo(): number {
    return this.sanduiche.custo() + 4.5;
  }
}

class Pepperoni extends AdicionalDecorator {
  constructor(sanduiche: Sanduiche) {
    super(sanduiche);
  }

  descricao(): string {
    return this.sanduiche.descricao() + ", Pepperoni";
  }

  custo(): number {
    return this.sanduiche.custo() + 0.99;
  }
}
class QueijoMussarelaRalado extends AdicionalDecorator {
  constructor(sanduiche: Sanduiche) {
    super(sanduiche);
  }

  descricao(): string {
    return this.sanduiche.descricao() + ", Queijo Mussarela Ralado";
  }

  custo(): number {
    return this.sanduiche.custo() + 2.0;
  }
}
let sanduiche: Sanduiche = new SanduicheBasico();
sanduiche = new FrangoAssado(sanduiche);
sanduiche = new Pepperoni(sanduiche);
sanduiche = new QueijoMussarelaRalado(sanduiche);

console.log(`${sanduiche.descricao()} custa $${sanduiche.custo().toFixed(2)}.`);




```
