# React

React é uma biblioteca JavaScript utilizada para construir interfaces de usuário. Ela permite dividir a interface em componentes reutilizáveis, organizar a aplicação em partes menores e atualizar a tela conforme os dados mudam.

Este repositório reúne materiais de estudo, explicações e exemplos de código sobre os principais conceitos do React. O conteúdo pode ser utilizado como referência para aprender a biblioteca, revisar conceitos ou desenvolver atividades práticas.

## Principais conceitos

- **JSX:** sintaxe que permite descrever elementos de interface dentro do JavaScript.
- **Componentes:** blocos reutilizáveis que representam partes da interface.
- **Props:** dados passados de um componente para outro.
- **State:** dados que podem mudar durante o uso da aplicação e provocar uma nova renderização.
- **Renderização de listas e condicional:** formas de apresentar conteúdo de acordo com os dados disponíveis.
- **Hooks:** funções como `useState` e `useEffect`, usadas para trabalhar com estado e efeitos em componentes funcionais.
- **Consumo de APIs:** integração da interface com serviços externos.
- **Navegação:** organização de páginas e rotas com bibliotecas como React Router.

## Conteúdo do repositório

1. [JSX](01-jsx.md)
2. [Componentes](02-componentes.md)
3. [Props](03-props.md)
4. [Virtual DOM](04-virtual-dom.md)
5. [Listas e key](05-listas-e-key.md)
6. [Renderização condicional](06-renderizacao-condicional.md)
7. [State e useState](07-state-usestate.md)
8. [Formulários em React](08-formularios.md)
9. [useEffect](09-useeffect.md)
10. [Consumo de APIs](10-consumo-de-apis.md)
11. [React Router](11-react-router.md)

## Exemplos de código

### 1. Criando um elemento com JSX

JSX permite descrever a estrutura da interface usando uma sintaxe semelhante a HTML dentro do JavaScript.

```jsx
const titulo = <h1>Olá, React!</h1>;
```

### 2. Criando um componente

Componentes são funções que retornam elementos da interface e podem ser reutilizados em diferentes partes da aplicação.

```jsx
function BoasVindas() {
  return <p>Bem-vindo ao mundo do React!</p>;
}

export default BoasVindas;
```

### 3. Utilizando props

As props permitem que um componente receba dados de quem o utiliza.

```jsx
function Saudacao({ nome }) {
  return <p>Olá, {nome}!</p>;
}

// Exemplo de uso:
// <Saudacao nome="Ana" />
```

### 4. Gerenciando estado

O hook `useState` permite armazenar e atualizar informações que afetam a interface.

```jsx
import { useState } from "react";

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <button onClick={() => setContador(contador + 1)}>
      Cliques: {contador}
    </button>
  );
}
```

## Estrutura dos arquivos

```text
aula-react/
├── README.md
├── 01-jsx.md
├── 02-componentes.md
├── 03-props.md
├── 04-virtual-dom.md
├── 05-listas-e-key.md
├── 06-renderizacao-condicional.md
├── 07-state-usestate.md
├── 08-formularios.md
├── 09-useeffect.md
├── 10-consumo-de-apis.md
└── 11-react-router.md
```

## Documentação e referências

- [Documentação oficial do React](https://react.dev/)
- [Aprenda os fundamentos do React](https://react.dev/learn)
- [Documentação do React Router](https://reactrouter.com/)

## Observação

Os arquivos deste repositório são materiais de referência em Markdown. Os exemplos servem para estudo e podem precisar ser inseridos em um projeto React configurado para serem executados.
