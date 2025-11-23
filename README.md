class ContaBancaria {
    constructor(titular, saldo = 0) {
        this.titular = titular;
        this.saldo = saldo;
    }

    depositar(valor) {
        this.saldo += valor;
        console.log(`Depósito de R$${valor} realizado. Novo saldo: R$${this.saldo}`);
    }

    sacar(valor) {
        if (valor > this.saldo) {
            console.log("Saldo insuficiente!");
            return;
        }
        this.saldo -= valor;
        console.log(`Saque de R$${valor} realizado. Novo saldo: R$${this.saldo}`);
    }
}

// Exemplo:
const conta = new ContaBancaria("João", 100);
conta.depositar(50);
conta.sacar(30);

class Livro {
    constructor(titulo, autor, paginas, lido = false) {
        this.titulo = titulo;
        this.autor = autor;
        this.paginas = paginas;
        this.lido = lido;
    }

    marcarComoLido() {
        this.lido = true;
        console.log(`O livro "${this.titulo}" foi marcado como lido.`);
    }
}

// Exemplo:
const livro = new Livro("1984", "George Orwell", 328);
livro.marcarComoLido();

class Produto {
    constructor(nome, preco, quantidade) {
        this.nome = nome;
        this.preco = preco;
        this.quantidade = quantidade;
    }

    valorTotal() {
        return this.preco * this.quantidade;
    }
}

// Exemplo:
const produto = new Produto("Mouse", 50, 10);
console.log("Valor total em estoque:", produto.valorTotal());

class Temperatura {
    constructor(valorCelsius) {
        this.valor = valorCelsius;
    }

    paraFahrenheit() {
        return (this.valor * 9/5) + 32;
    }

    paraKelvin() {
        return this.valor + 273.15;
    }
}

// Exemplo:
const temp = new Temperatura(25);
console.log("Fahrenheit:", temp.paraFahrenheit());
console.log("Kelvin:", temp.paraKelvin());


class Agenda {
    constructor() {
        this.compromissos = [];
    }

    adicionar(compromisso) {
        this.compromissos.push(compromisso);
    }

    listar() {
        console.log("Compromissos:");
        this.compromissos.forEach((c, i) => {
            console.log(`${i + 1}. ${c}`);
        });
    }
}

// Exemplo:
const agenda = new Agenda();
agenda.adicionar("Consulta médica");
agenda.adicionar("Reunião às 14h");
agenda.listar();
