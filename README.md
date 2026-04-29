# 🚀 Guia Intermediário: Arrays, Objetos e Funções no JavaScript

Seja bem-vindo! Neste material, vamos desmistificar as principais estruturas do JavaScript. Se você tem dificuldade de visualizar como o código funciona, não se preocupe. Vamos conectar a programação com coisas que você já conhece: calculadoras, diários de classe e boletins escolares.

---

## 1. Arrays: A Lista de Chamada

* **O que é?** Um Array (ou vetor) é uma **lista organizada** de dados. Pense nos armários numerados do laboratório ou nas linhas de uma planilha do Excel. Cada informação fica em uma "gaveta" que possui um número de identificação chamado **índice**.
* **Regra de Ouro:** Na programação, começamos a contar do **Zero (0)**!
* **Onde se aplica?** Listas de notas, nomes de alunos matriculados, histórico de cálculos em uma calculadora.



```javascript
// Criando um histórico de notas de um aluno (Array de Números)
const notasDoSemestre = [8.5, 7.0, 9.5, 6.0];
// Índices:               0    1    2    3

// Como acessar a primeira nota?
console.log(notasDoSemestre[0]); // Saída: 8.5

// Como adicionar a nota de um trabalho extra no final da lista?
notasDoSemestre.push(10.0);
console.log(notasDoSemestre); // [8.5, 7.0, 9.5, 6.0, 10.0]
```

---

## 2. Objetos Literais: A Ficha de Matrícula

* **O que é?** Enquanto o Array é uma lista de várias coisas, o **Objeto** é a descrição detalhada de **uma única entidade**. Ele guarda informações em formato de **Chave: Valor**.
* **Por que usar?** Para manter dados relacionados agrupados. Em vez de ter várias variáveis soltas (`nome`, `idade`, `curso`), você cria um único bloco de informações.
* **Onde se aplica?** O perfil de um usuário no sistema da escola, a configuração de uma prova online.



```javascript
// Criando o objeto de um aluno da ETEC
const alunoPerfil = {
  nome: "Ana Clara",
  ra: "123456",
  curso: "Desenvolvimento de Sistemas",
  matriculaAtiva: true
};

// Como acessar o curso da Ana? Usamos o PONTO (.)
console.log(alunoPerfil.curso); // Saída: "Desenvolvimento de Sistemas"
```

---

## 3. Funções: O Motor da Calculadora

* **O que é?** Uma Função é um bloco de código que faz um trabalho específico. Imagine os botões de uma calculadora científica: cada botão (soma, raiz quadrada, porcentagem) é uma função que fica ali, esperando você apertar para agir.



### 3.1 Funções Void vs. Funções com Retorno

* **Função com Retorno (`return`):** É como a operação de Soma da calculadora. Você entrega dois números (parâmetros), ela faz a conta no processador, e **te devolve** o resultado no visor.
* **Função Void (Vazia/Sem Retorno):** É como o botão "Clear" (C) da calculadora ou o sinal de fim de aula. Ela executa uma ação (limpar a tela, tocar um som, imprimir uma mensagem), mas não devolve um valor matemático ou de texto para você guardar em uma variável.

```javascript
// Exemplo de Função com Retorno (Calculadora)
function somar(numero1, numero2) {
    let resultado = numero1 + numero2;
    return resultado; // Devolve a resposta
}
const total = somar(5, 7); // A variável 'total' guarda o número 12

// Exemplo de Função Void (Aviso na tela)
function exibirAlertaDeProva() {
    console.log("Atenção: Faltam 10 minutos para o fim da avaliação!");
    // Não tem 'return', apenas executa uma ação.
}
exibirAlertaDeProva();
```

### 3.2 O Poder dos Parâmetros e Valores Padrão (Default)
Parâmetros são os dados que a função precisa para trabalhar. E se o usuário esquecer de enviar uma informação? Nós usamos os **Valores Padrão**.

```javascript
// Se não informarem o divisor, o padrão será 1 (para evitar erros de divisão)
function dividir(dividendo, divisor = 1) {
    return dividendo / divisor;
}

console.log(dividir(10, 2)); // Saída: 5
console.log(dividir(10));    // Saída: 10 (usou o divisor padrão 1)
```

---

## 4. Os 3 Tipos de Funções no JavaScript



### A. Função Declarada (Function Declaration)
A forma clássica. Ela sofre o efeito de **Hoisting** (elevação), o que significa que o JavaScript lê essas funções antes de rodar o código. Você pode "chamar" a função antes da linha onde ela foi escrita.

```javascript
// Chamando antes da declaração!
exibirCabecalho("Aula de Lógica"); 

function exibirCabecalho(materia) {
    console.log(`--- SISTEMA ACADÊMICO: ${materia} ---`);
}
```

### B. Função Expressa (Function Expression)
Aqui, a função é guardada dentro de uma variável. Ela **não** sofre Hoisting. É muito útil quando você quer tratar uma função como se fosse um dado qualquer, garantindo a ordem exata de execução.

```javascript
// A função "nasce" na variável
const calcularMedia = function(n1, n2) {
    return (n1 + n2) / 2;
};

console.log(calcularMedia(8, 6)); // Saída: 7
```



### C. Arrow Function (`=>`)
A queridinha do JavaScript moderno. É uma versão curta e limpa da função expressa. É ideal para fórmulas matemáticas diretas e para manipular dados dentro de arrays.

```javascript
// Arrow function padrão
const subtrair = (a, b) => {
    return a - b;
};

// Arrow function concisa: Se tiver só UMA linha, tira-se as chaves {} e o 'return' é invisível/automático!
const dobrarValor = x => x * 2;

console.log(dobrarValor(5)); // Saída: 10
```

---

## 🤯 Estruturas Complexas: Misturando Arrays e Objetos

Onde a programação encontra a vida real! Um sistema escolar não é feito só de notas soltas, mas de **Listas contendo Fichas de Alunos**.

### A. Array de Objetos (Diário de Classe)
Uma lista (Array) onde cada item é um aluno (Objeto).

```javascript
const turmaDesenvolvimento = [
  { ra: 101, nome: "Carlos", notaFinal: 8.5 }, // Índice 0
  { ra: 102, nome: "Beatriz", notaFinal: 5.0 }, // Índice 1
  { ra: 103, nome: "João", notaFinal: 9.0 }     // Índice 2
];

// Acessando a nota da Beatriz:
console.log(turmaDesenvolvimento[1].notaFinal); // Saída: 5.0
```

### B. Objeto com Arrays (Boletim Escolar)
Um documento único (Objeto) que guarda, entre outras coisas, uma lista de notas do bimestre (Array).

```javascript
const boletim = {
  aluno: "Lucas Mendes",
  disciplina: "Programação Web",
  notasBimestrais: [7.5, 8.0, 6.5, 9.0] // Um array dentro do objeto!
};

// Acessando a terceira nota do Lucas no bimestre:
console.log(boletim.notasBimestrais[2]); // Saída: 6.5
```

---

## 🏋️‍♂️ Laboratório de Algoritmos: 10 Exercícios Práticos

Estes exercícios têm um nível de dificuldade progressivo. Tente fazer um por um, usando o console do navegador ou o Node.js.

### Nível 1: Aquecimento de Memória
**1.** Crie um **Array** chamado `linguagens` contendo as strings "JavaScript", "Python" e "Java". Imprima a segunda linguagem no console.
**2.** Crie um **Objeto** chamado `prova` com as propriedades: `materia` (string), `peso` (número) e `aplicada` (booleano - true/false).
**3.** Crie uma **Função Declarada** (void) chamada `iniciarCalculadora` que imprima no console a frase: *"Calculadora inicializada com sucesso!"*.

### Nível 2: Processamento e Funções
**4.** Crie uma **Função Expressa** chamada `calcularAreaRetangulo` que receba `base` e `altura` como parâmetros e **retorne** a multiplicação entre eles.
**5.** Crie uma **Arrow Function concisa** (de uma linha só) chamada `elevarAoQuadrado` que receba um número `x` e retorne `x * x`.
**6.** Crie uma função chamada `gerarRelatorio(nomeAluno, status = "Pendente")`. Se você chamar a função passando apenas o nome, ela deve imprimir: *"Relatório do aluno [nome] está Pendente"*. Teste a função.

### Nível 3: Integração de Estruturas
**7.** Crie um **Objeto** chamado `historicoMatematico`. Ele deve ter a propriedade `operacao` (string, ex: "Soma") e a propriedade `valoresParticipantes`, que deve ser um **Array** de números (ex: `[5, 10, 15]`).
**8.** Crie um **Array de Objetos** chamado `listaDeProvas`. Adicione 3 objetos dentro dele. Cada objeto deve representar uma prova com `disciplina` (string) e `notaTirada` (número).

### Nível 4: Lógica Aplicada (Desafios)
**9. A Função Filtro:** Crie uma função chamada `filtrarAprovados` que receba o array `listaDeProvas` (criado no ex. 8). Use um laço (`for` ou `forEach`) para percorrer o array e imprimir no console **apenas** as disciplinas em que a `notaTirada` foi maior ou igual a 6.0.
**10. A Calculadora de Média (O Desafio Final):** * Crie um objeto chamado `sistemaEscolar`. 
* Dentro dele, coloque uma propriedade `nomeDoAluno`.
* Adicione uma propriedade `notas`, que será um **Array** com 4 números.
* Crie um **método** (uma função atrelada ao objeto) chamado `calcularMediaGeral`. Esse método deve somar todos os valores do array de notas, dividir pelo tamanho do array (`.length`) e retornar a média exata.
* Execute `sistemaEscolar.calcularMediaGeral()` e imprima o resultado!
