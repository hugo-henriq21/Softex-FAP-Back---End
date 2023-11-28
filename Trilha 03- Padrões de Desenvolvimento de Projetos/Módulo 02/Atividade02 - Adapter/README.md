# Instruções:

Crie um adaptador que permita que um objeto do tipo <b>Pato</b>  seja usado como se fosse um objeto do tipo <b> Galinha</b> 
Siga o exemplo apresentado no Hipertexto 4 e crie as classes <b>AdaptadorPato </b> e  <b>AdaptadorPatoDemo</b>  para demonstrar o uso da classe  <b>AdaptadorPato</b>

## CÓDIGO EM TypesCript

```JS
interface Galinha {
  ciscar(): void;
}
class Pato {
  nadar(): void {
    console.log('O pato está nadando');
  }
}
class AdaptadorPato implements Galinha {
  private pato: Pato;

  constructor(pato: Pato) {
    this.pato = pato;
  }

  ciscar(): void {
    console.log('Ciscar está adaptado:');
    this.pato.nadar();
  }
}
class AdaptadorPatoDemo {
  runDemo(): void {
    // objeto Pato
    const pato = new Pato();

    // adaptador para o Pato
    const adaptadorPato = new AdaptadorPato(pato);

    // adaptador como se fosse uma Galinha
    adaptadorPato.ciscar();
  }
}
const demo = new AdaptadorPatoDemo();
demo.runDemo();

```
