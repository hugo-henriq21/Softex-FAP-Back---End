# Instruções:

Considere que:

os produtos devem implementar uma interface comum;
o cliente deve utilizar apenas a fábrica para criar instâncias do tipo abstrato da interface;
todo computador deve ter, com getters, os atributos: ram, hdd, cpu e type;
há dois tipos de computadores: pc e server; - RAM e HD devem estar em GB;
CPU deve estar em GHz;
através do tipo informado, a fábrica decide qual tipo de computador irá instanciar;
quando o método .toString() for aplicado a um computador, ele deve imprimir seus atributos.

# RESPOSTA

## CÓDIGO EM JS
 ``` JS
// Criação da Interface 
class Computador {
    constructor(ram, hdd, cpu, type) {
      this.cpu = cpu;
      this.type = type;
      this.ram = ram;
      this.hdd = hdd;
    }

    toString() {
      return `Computador Tipo: ${this.type}, RAM: ${this.ram}GB, HDD: ${this.hdd}GB, CPU: ${this.cpu}GHz`;
    }
  }

  class FactoryComputador {
    createComputer(type, ram, hdd, cpu) {
      if (type === 'pc') {
        return new Computador(ram, hdd, cpu, 'pc');
      } else if (type === 'server') {
        return new Computador(ram, hdd, cpu, 'server');
      } else {
        throw new Error('Tipo de computador não suportado');
      }
    }
  }

  const fabrica = new FactoryComputador();
  const pc = fabrica.createComputer('pc', 5, 1004, 6.8);
  const server = fabrica.createComputer('server', 64, 256, 1.2);

  console.log(pc.toString());     
  console.log(server.toString());  


```
