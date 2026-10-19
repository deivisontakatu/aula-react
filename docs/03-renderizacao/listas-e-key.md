# Listas e key

## 1. Objetivos de aprendizagem

- Renderizar listas a partir de arrays.
- Utilizar `map()` para transformar dados em elementos.
- Entender por que cada item precisa de uma `key` estável.

## 2. O problema

Catálogos, tarefas e listas de usuários têm conteúdo repetido com dados diferentes. Escrever cada elemento manualmente dificulta atualizações e manutenção.

## 3. Conceito

O método `map()` permite transformar cada registro em um elemento React. Ao renderizar uma coleção, cada elemento irmão precisa de uma `key` estável e única dentro daquela lista. A chave ajuda o React a identificar os itens entre renderizações; normalmente, usamos um identificador do dado.

## 4. Demonstração do professor

```jsx
const conceitos = [
  { id: "jsx", titulo: "JSX" },
  { id: "props", titulo: "Props" },
  { id: "state", titulo: "State" },
];

function ConceptList() {
  return (
    <ul>
      {conceitos.map((conceito) => (
        <li key={conceito.id}>{conceito.titulo}</li>
      ))}
    </ul>
  );
}
```

Explique que a `key` é uma informação usada pelo React e não é recebida automaticamente como prop pelo componente filho.

## 5. Reprodução do aluno

1. Crie um array de conceitos.
2. Use `map()` para produzir itens da lista.
3. Defina um identificador para cada item.
4. Use esse identificador como `key`.
5. Adicione ou remova um item e observe o resultado.

## 6. Desafio prático

Crie uma lista de tarefas com identificadores estáveis e adicione uma forma de destacar as tarefas concluídas.

## 7. Erros comuns

- Esquecer a prop `key`.
- Usar o índice como chave em listas que podem ser reordenadas, inseridas ou removidas.
- Reutilizar identificadores duplicados na mesma lista.
- Esperar que `key` esteja disponível como uma prop comum.

## 8. Checklist

- [ ] Sei transformar dados em elementos com `map()`.
- [ ] Entendo o propósito de `key`.
- [ ] Escolho chaves estáveis sempre que possível.

## 9. Próximo passo

Estude como o React coordena renderizações e reconciliação quando dados e estrutura mudam.
