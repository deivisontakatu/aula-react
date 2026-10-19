# Aula 2 — Componentes

## Objetivos de aprendizagem

Compreender o papel dos componentes, identificar responsabilidades em uma interface e entender como componentes formam uma árvore reutilizável.

## 1. O que é um componente?

Um componente é uma unidade independente e reutilizável da interface. Em React, componentes são normalmente funções JavaScript que recebem entradas e retornam elementos React, frequentemente escritos em JSX.

~~~jsx
function Cabecalho() {
  return <header><h1>React Lab</h1></header>;
}
~~~

O componente descreve um cabeçalho que pode ser utilizado em outras partes da aplicação sem copiar sua marcação.

## 2. Por que dividir uma interface?

Uma página pode conter cabeçalho, menu, cartões, filtros, formulário e rodapé. Manter tudo em um único componente pode dificultar a leitura e tornar alterações mais arriscadas.

A divisão em componentes ajuda a separar responsabilidades, reutilizar estruturas, facilitar testes e manutenção e dar nomes claros às partes da interface.

## 3. Como um componente é utilizado?

Componentes com nomes iniciados por letra maiúscula são utilizados no JSX como elementos.

~~~jsx
function Cabecalho() {
  return <h1>Catálogo React</h1>;
}

function App() {
  return (
    <main>
      <Cabecalho />
      <p>Explore os principais conceitos.</p>
    </main>
  );
}
~~~

App utiliza Cabecalho como parte de sua estrutura. Essa composição é um dos princípios centrais do React.

## 4. Árvore de componentes

A interface pode ser entendida como uma árvore: um componente principal contém componentes filhos, que por sua vez podem conter outros componentes.

Exemplo de um catálogo:

- App
  - Cabecalho
  - BarraDePesquisa
  - ListaDeConceitos
    - CardConceito
    - CardConceito
  - Rodape

Essa organização ajuda a compreender onde cada responsabilidade fica localizada e como os dados podem ser passados entre as partes.

## 5. Componentes e reutilização

Um componente reutilizável descreve uma estrutura geral. Os dados específicos de cada uso podem ser recebidos por props, assunto da próxima aula.

Reutilização não significa criar um componente para absolutamente todo elemento HTML. A divisão deve facilitar a compreensão, a manutenção ou a consistência visual.

## 6. Regras e boas práticas

- Os nomes dos componentes devem começar com letra maiúscula.
- Componentes devem ter responsabilidades claras.
- Evite componentes gigantes que concentrem toda a aplicação.
- Evite fragmentar tanto que a leitura fique mais difícil.
- Componentes devem evitar efeitos colaterais inesperados durante a renderização.
- Componentes podem ser exportados para uso em outros arquivos.

## 7. Erros comuns

- Escrever o nome de um componente com letra minúscula no JSX.
- Confundir a definição da função com sua utilização como elemento.
- Repetir a mesma estrutura em muitos lugares sem avaliar a reutilização.
- Criar componentes que dependem excessivamente de detalhes internos de outros componentes.

## Resumo

Componentes são os blocos fundamentais de uma interface React. Eles permitem decompor telas em unidades menores, compor estruturas maiores e reutilizar a apresentação de forma consistente.

## Para refletir

1. Quais componentes você identificaria em uma loja virtual?
2. Quando vale a pena transformar um trecho da interface em componente?
3. Como uma árvore de componentes ajuda a compreender uma aplicação?

## Referências

- [React — Seu primeiro componente](https://react.dev/learn/your-first-component)
- [React — Importando e exportando componentes](https://react.dev/learn/importing-and-exporting-components)
- [React — Passando props para um componente](https://react.dev/learn/passing-props-to-a-component)

## Exemplos adicionais de código

### Exemplo 1 — Componente de rodapé
~~~jsx
function Rodape() {
  return <footer>React Lab — Material de estudo</footer>;
}
~~~

### Exemplo 2 — Composição de componentes
~~~jsx
function App() {
  return (
    <main>
      <Cabecalho />
      <ConteudoPrincipal />
      <Rodape />
    </main>
  );
}
~~~

### Exemplo 3 — Componente com estrutura reutilizável
~~~jsx
function Secao({ children }) {
  return <section className="secao">{children}</section>;
}

// Uso: <Secao><p>Conteúdo da aula</p></Secao>
~~~
