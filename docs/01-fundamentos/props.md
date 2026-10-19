# Props

## 1. Objetivos de aprendizagem

- Explicar o papel das props.
- Passar dados de um componente pai para um filho.
- Reutilizar o mesmo componente com conteúdos diferentes.

## 2. O problema

Um componente de card não deveria precisar ser reescrito para cada título, descrição ou categoria. Os dados devem ser informados de fora, enquanto a estrutura visual permanece reutilizável.

## 3. Conceito

Props são entradas fornecidas a um componente. Elas permitem que um componente pai configure a apresentação ou o comportamento de um componente filho. Props devem ser tratadas como somente leitura: o componente não deve alterá-las diretamente.

## 4. Demonstração do professor

```jsx
function ConceptCard({ titulo, descricao }) {
  return (
    <article>
      <h2>{titulo}</h2>
      <p>{descricao}</p>
    </article>
  );
}

function App() {
  return (
    <>
      <ConceptCard titulo="JSX" descricao="Sintaxe para descrever interfaces." />
      <ConceptCard titulo="Props" descricao="Dados enviados entre componentes." />
    </>
  );
}
```

Mostre como os dois cards compartilham a estrutura, mas exibem dados diferentes.

## 5. Reprodução do aluno

1. Crie um componente `ConceptCard`.
2. Receba título e descrição como props.
3. Renderize dois cards com conteúdos diferentes.
4. Acrescente uma prop de categoria.
5. Teste o resultado.

## 6. Desafio prático

Crie um card de livro com título, autor e situação de leitura. Use o mesmo componente para representar três livros.

## 7. Erros comuns

- Alterar diretamente uma prop.
- Confundir props com estado local.
- Esquecer de passar uma prop exigida pelo componente.
- Esperar que uma prop provoque mudanças por si só sem uma nova renderização causada pelo fluxo normal do React.

## 8. Checklist

- [ ] Sei passar props.
- [ ] Consigo reutilizar um componente com valores diferentes.
- [ ] Entendo que props são somente leitura.

## 9. Próximo passo

Use `useState` quando um componente precisar manter dados que mudam em resposta a interações.
