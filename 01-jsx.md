# Aula 1 — JSX

## Objetivos de aprendizagem

Compreender o que é JSX, por que ele é utilizado no React e como combina a descrição de uma interface com expressões JavaScript.

## 1. O que é JSX?

JSX é uma extensão de sintaxe para JavaScript que permite escrever uma estrutura semelhante a HTML dentro do código JavaScript. É muito utilizada para descrever a interface dos componentes React.

~~~jsx
const titulo = <h1>Olá, React!</h1>;
~~~

Esse trecho descreve um elemento de interface. Ele não é uma string HTML e não é inserido diretamente no navegador como texto. Durante o processo de compilação, ferramentas transformam JSX em JavaScript que descreve elementos React.

## 2. Por que utilizar JSX?

Sem JSX, criar árvores de elementos pode exigir chamadas de funções mais extensas e difíceis de visualizar. JSX aproxima a estrutura visual da lógica que a produz, tornando a leitura e a manutenção mais simples.

Principais vantagens:

- Permite visualizar a estrutura da interface no próprio código.
- Facilita combinar marcação e expressões JavaScript.
- Ajuda a organizar a interface dentro de componentes.
- Torna mais clara a relação entre dados e conteúdo exibido.

## 3. Expressões JavaScript

Chaves permitem inserir expressões JavaScript dentro do JSX.

~~~jsx
const nome = "Marina";
const saudacao = <h1>Olá, {nome}!</h1>;
~~~

Também podemos utilizar expressões:

~~~jsx
const a = 10;
const b = 5;
const resultado = <p>Soma: {a + b}</p>;
~~~

Dentro das chaves, usamos expressões que produzem um valor. Instruções como if e for não são colocadas diretamente dentro de uma expressão JSX; normalmente usamos condições antes do retorno, operador ternário ou métodos de array.

## 4. Diferenças entre JSX e HTML

Embora sejam parecidos, há diferenças importantes:

- Em geral, usamos className em vez de class.
- Atributos seguem convenções JavaScript, como htmlFor.
- Elementos sem conteúdo precisam ser fechados, por exemplo <img />.
- Um componente deve retornar uma estrutura com um elemento raiz ou usar um Fragment.
- Valores dinâmicos são inseridos por meio de chaves.

## 5. JSX e segurança

O React escapa valores de texto inseridos normalmente no JSX, reduzindo o risco de interpretar texto fornecido por usuários como marcação HTML. Recursos que inserem HTML bruto exigem cuidado especial e sanitização apropriada.

## 6. Exemplo conceitual

~~~jsx
function Saudacao() {
  const nome = "Lucas";

  return (
    <section>
      <h1>Bem-vindo, {nome}!</h1>
      <p>Este é o React Lab.</p>
    </section>
  );
}
~~~

A função descreve uma seção com um título personalizado e um parágrafo. A variável nome é utilizada como parte do conteúdo.

## 7. Erros comuns

- Tratar JSX como uma string HTML.
- Esquecer de fechar elementos.
- Usar class em vez de className.
- Colocar instruções completas diretamente entre chaves.
- Confundir a descrição de um elemento com a inserção imediata dele no DOM.

## Resumo

JSX é uma sintaxe que torna mais expressiva a descrição das interfaces React. Ele combina uma estrutura semelhante a HTML com expressões JavaScript e é transformado em JavaScript antes de ser executado.

## Para refletir

1. Por que JSX facilita a leitura de interfaces?
2. Qual é a diferença entre JSX e HTML?
3. Para que servem as chaves dentro do JSX?

## Referências

- [React — Escrevendo marcação com JSX](https://react.dev/learn/writing-markup-with-jsx)
- [React — JavaScript em JSX com chaves](https://react.dev/learn/javascript-in-jsx-with-curly-braces)

## Exemplos adicionais de código

### Exemplo 1 — Atributos JSX
~~~jsx
function LinkDocumentacao() {
  return (
    <a href="https://react.dev" className="link">
      Documentação do React
    </a>
  );
}
~~~

### Exemplo 2 — Expressões e cálculos
~~~jsx
function ResumoPedido() {
  const quantidade = 3;
  const preco = 12;

  return <p>Total: R$ {quantidade * preco}</p>;
}
~~~

### Exemplo 3 — Fragment
~~~jsx
function Perfil() {
  return (
    <>
      <h2>Camila Souza</h2>
      <p>Estudante de desenvolvimento web</p>
    </>
  );
}
~~~
