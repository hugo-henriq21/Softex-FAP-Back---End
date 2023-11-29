# Instruções:

Aplique o padrão de projeto <i>Observer</i> para criar um simples editor de texto. Considere a solução apresentada no Hipertexto 6 e utilize o código visto para implementar novas classes. Os requisitos para avaliar o projeto são: 
 - implementar uma subclasse da classe <b>Editor</b>  chamada <b>TextEditor</b>
- aplicar o método <b>insertLine</b> , que recebe os parâmetros <b> lineNumber</b>  e  <b>text</b>
- inserir o texto na ordem correspondente a lineNumber  e deslocar as linhas posteriores se necessário; 
- aplicar o método <b>removeLine</b> , que recebe <b>lineNumber</b>  como parâmetro, deleta o texto da linha correspondente e desloca as linhas posteriores se necessário; 
- instanciar um <b>TextEditor</b> e disparar o evento “<i>open</i>";
- receber as linhas de texto, que serão inseridas no objeto <b>textEditor</b>, do usuário até que ele envie o texto “EOF”, que não deve ser inserido no objeto <b>textEditor</b>
- por fim, o <b>textEditor</b> deve disparar o evento “<i>save</i>” para que o conteúdo seja salvo no arquivo configurado e imprimir todo o conteúdo do arquivo na tela. 

## CÓDIGO EM JS

```JS

// Classe base Observer
class Observer {
    update(): void {}
}

class Subject {
    private observers: Observer[] = [];

    addObserver(observer: Observer): void {
        this.observers.push(observer);
    }

    removeObserver(observer: Observer): void {
        this.observers = this.observers.filter((obs) => obs !== observer);
    }

    notifyObservers(): void {
        this.observers.forEach((observer) => observer.update());
    }
}
class Editor extends Subject {
    private content: string[] = [];

    getContent(): string[] {
        return this.content;
    }

    setContent(content: string[]): void {
        this.content = content;
        this.notifyObservers();
    }
}
class TextEditor extends Editor {
    insertLine(lineNumber: number, text: string): void {
        this.content.splice(lineNumber, 0, text);
        this.notifyObservers();
    }

    removeLine(lineNumber: number): void {
        this.content.splice(lineNumber, 1);
        this.notifyObservers();
    }
}
class TextObserver extends Observer {
    private textEditor: TextEditor;

    constructor(textEditor: TextEditor) {
        super();
        this.textEditor = textEditor;
        this.textEditor.addObserver(this);
    }

    update(): void {
        console.log("Conteúdo Atualizado:", this.textEditor.getContent());
    }
}
const textEditor = new TextEditor();
const textObserver = new TextObserver(textEditor);

console.log("Digite linhas de texto. Digite 'EOF' para salvar e encerrar.");

let lineNumber = 0;
let inputText = prompt(`Linha ${lineNumber + 1}: `);

while (inputText && inputText.toUpperCase() !== "EOF") {
    textEditor.insertLine(lineNumber, inputText);
    lineNumber++;
    inputText = prompt(`Linha ${lineNumber + 1}: `);
}

textEditor.notifyObservers(); 

console.log("Conteúdo Salvo e Exibido:");
console.log(textEditor.getContent());


```
