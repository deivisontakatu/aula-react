# useCallback

## 1. Objetivos de aprendizagem

- Explicar o que `useCallback` memoriza.
- Identificar cenários em que a identidade de uma função importa.
- Evitar otimização prematura.

## 2. O problema

Em React, uma função declarada dentro de um componente normalmente recebe uma nova identidade em cada renderização. Em situações específicas, essa mudança pode invalidar uma otimização de um componente filho ou de outro Hook.

## 3. Conceito

`useCallback` permite reutilizar a mesma função entre renderizações enquanto suas dependências não mudam. Isso costuma ser útil junto a componentes memoizados ou Hooks que dependem da identidade da função. Não é necessário utilizá-lo em toda função.

## 4. Demonstração do professor

```jsx
import { useCallback, useState } from "react";

function SearchPanel() {
  const [query, setQuery] = useState("");
  const handleChange = useCallback((event) => {
    setQuery(event.target.value);
  }, []);

  return <input value={query} onChange={handleChange} />;
}
```

Mostre a sintaxe e explique que, neste exemplo isolado, a memoização pode não oferecer benefício perceptível. O foco é entender o mecanismo, não recomendar seu uso indiscriminado.

## 5. Reprodução do aluno

1. Crie um componente com estado.
2. Declare uma função manipuladora.
3. Envolva a função em `useCallback`.
4. Identifique quais valores externos a função utiliza.
5. Discuta quando a estabilidade da função faria diferença.

## 6. Desafio prático

Desenhe um cenário em que um componente filho memoizado recebe uma função por prop. Explique como uma função com identidade estável pode evitar renderizações desnecessárias nesse cenário.

## 7. Erros comuns

- Usar `useCallback` em todas as funções por padrão.
- Esquecer dependências necessárias.
- Confundir `useCallback` com a execução da função.
- Achar que a memoização elimina toda renderização do componente.

## 8. Checklist

- [ ] Sei o que é identidade de uma função.
- [ ] Entendo o objetivo de `useCallback`.
- [ ] Consigo justificar quando uma otimização é útil.

## 9. Próximo passo

Estude roteamento para organizar múltiplas telas em uma aplicação.
