# Aula React

Material didático teórico para um curso introdutório de React com carga horária sugerida de 20 horas.

Cada arquivo Markdown corresponde a uma aula sobre um conceito da biblioteca, com explicações, exemplos e pontos de atenção. A proposta é permitir que o professor apresente o conceito, demonstre os exemplos e, em seguida, oriente a reprodução pelos estudantes.

## Trilha de aprendizagem

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

## Estrutura

~~~text
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
~~~

## Abordagem

- **Teoria primeiro:** definição, motivação, funcionamento e exemplos.
- **Demonstração e reprodução:** o professor demonstra os conceitos e os estudantes reproduzem e adaptam os exemplos.
- **Progressão:** a trilha parte da descrição da interface, passa por composição e interação e termina com integração externa e navegação.
- **Boas práticas:** atenção a imutabilidade, eventos, acessibilidade, estados de carregamento e erros.
- **Escopo:** somente documentação Markdown; não há aplicação React executável.

## Distribuição sugerida das 20 horas

| Conteúdo | Carga horária |
|---|---:|
| JSX | 1,5 h |
| Componentes | 2 h |
| Props | 1,5 h |
| Virtual DOM | 1 h |
| Listas e key | 1 h |
| Renderização condicional | 1 h |
| State, useState e eventos | 3 h |
| Formulários | 2 h |
| useEffect | 2 h |
| Consumo de APIs | 2,5 h |
| React Router | 1,5 h |
| **Total** | **20 h** |

## Referências principais

- [Documentação oficial do React](https://react.dev/learn)
- [Renderização condicional](https://react.dev/learn/conditional-rendering)
- [Renderizando listas](https://react.dev/learn/rendering-lists)
- [Documentação do React Router](https://reactrouter.com/)

## Exemplos rápidos de código

Os trechos abaixo são exemplos introdutórios de React. Os demais arquivos aprofundam cada conceito com exemplos específicos.

**Exemplo 1 — JSX**
~~~jsx
const titulo = <h1>React Lab</h1>;
~~~

**Exemplo 2 — Componente**
~~~jsx
function BoasVindas() {
  return <p>Vamos aprender React!</p>;
}
~~~

**Exemplo 3 — Props**
~~~jsx
function Saudacao({ nome }) {
  return <p>Olá, {nome}!</p>;
}

// Uso: <Saudacao nome="Ana" />
~~~
