# Aula 3 — Props

## Objetivos de aprendizagem

Entender o que são props, como transportam dados entre componentes e por que permitem reutilizar a mesma estrutura com conteúdos diferentes.

## 1. O que são props?

Props, abreviação de properties, são entradas recebidas por um componente React. Elas permitem que um componente pai configure o conteúdo ou o comportamento de um componente filho.

Considere um card de conceito: todos os cards podem ter a mesma estrutura visual, mas cada um precisa de título e descrição diferentes. As props permitem fornecer esses valores.

~~~jsx
function CardConceito({ titulo, descricao }) {
  return (
    <article>
      <h2>{titulo}</h2>
      <p>{descricao}</p>
    </article>
  );
}
~~~

Ao utilizar esse componente, diferentes valores podem ser informados:

~~~jsx
<CardConceito titulo="JSX" descricao="Sintaxe para descrever interfaces." />
<CardConceito titulo="Props" descricao="Entradas recebidas por componentes." />
~~~

A estrutura é a mesma; os dados mudam.

## 2. Fluxo de dados

Em uma arquitetura comum, os dados fluem do componente pai para o filho por meio de props. Isso torna explícito de onde vêm as informações usadas na apresentação.

Um componente pai pode organizar uma lista de conceitos e passar os dados de cada conceito para um card. O card não precisa conhecer a origem dos dados: ele recebe os valores e os apresenta.

## 3. Props são somente leitura

Props devem ser tratadas como somente leitura. Um componente não deve modificar diretamente as props recebidas. Se uma informação precisa mudar como resultado de uma interação, normalmente essa mudança é gerenciada por estado no componente responsável, que pode então fornecer novas props aos filhos.

Essa regra torna o fluxo de dados mais previsível e facilita descobrir onde uma alteração deve ocorrer.

## 4. Tipos de valores

Props podem transportar diferentes tipos de valores, incluindo strings, números, booleanos, arrays, objetos, funções e outros elementos React.

~~~jsx
<Botao destaque={true} quantidade={3} />
~~~

Expressões JavaScript são passadas entre chaves. Strings podem ser informadas com aspas.

## 5. A prop children

A prop children representa o conteúdo colocado entre a abertura e o fechamento de um componente.

~~~jsx
function Painel({ children }) {
  return <section className="painel">{children}</section>;
}

<Painel>
  <p>Conteúdo apresentado dentro do painel.</p>
</Painel>
~~~

Esse padrão é útil para criar layouts, painéis, modais e contêineres reutilizáveis.

## 6. Props versus estado

| Props | Estado |
|---|---|
| São recebidas de um componente pai. | É mantido pelo componente ou por uma estrutura de estado. |
| São tratadas como somente leitura pelo componente que as recebe. | É atualizado por mecanismos próprios, como useState. |
| Configuram o componente. | Representa informação que pode mudar ao longo do tempo. |

Os dois mecanismos podem trabalhar juntos: o pai mantém estado e passa seu valor como prop ao filho.

## 7. Erros comuns

- Tentar alterar diretamente uma prop.
- Esquecer de passar um valor esperado.
- Confundir props com variáveis globais.
- Supor que a prop key de listas estará disponível automaticamente dentro do componente filho.
- Passar muitos dados sem organização clara.

## Resumo

Props são o mecanismo básico para configurar componentes e transportar dados do pai para o filho. Elas promovem reutilização e tornam as relações entre componentes explícitas.

## Para refletir

1. Como props tornam um card reutilizável?
2. Por que um componente não deve modificar diretamente suas props?
3. Qual é a diferença entre props e estado?

## Referências

- [React — Passando props para um componente](https://react.dev/learn/passing-props-to-a-component)
- [React — Passando JSX com children](https://react.dev/learn/passing-props-to-a-component#passing-jsx-as-children)

## Exemplos adicionais de código

### Exemplo 1 — Props com número e booleano
~~~jsx
function Progresso({ porcentagem, concluido }) {
  return (
    <p>
      {porcentagem}% — {concluido ? "Concluído" : "Em andamento"}
    </p>
  );
}

// Uso: <Progresso porcentagem={60} concluido={false} />
~~~

### Exemplo 2 — Valor padrão
~~~jsx
function BotaoAcao({ texto = "Continuar" }) {
  return <button>{texto}</button>;
}
~~~

### Exemplo 3 — Passando um objeto por prop
~~~jsx
function PerfilAluno({ aluno }) {
  return <p>{aluno.nome} — {aluno.curso}</p>;
}

const estudante = { nome: "Rafaela", curso: "ADS" };
// Uso: <PerfilAluno aluno={estudante} />
~~~
