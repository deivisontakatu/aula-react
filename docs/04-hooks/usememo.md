# useMemo

## 1. Objetivos de aprendizagem

- Explicar a finalidade de `useMemo`.
- Memorizar o resultado de um cálculo entre renderizações.
- Reconhecer que memoização é uma otimização, não um requisito de correção.

## 2. O problema

Alguns cálculos podem ser custosos quando repetidos em toda renderização. Em cenários específicos, podemos reutilizar o resultado calculado enquanto suas dependências não mudam.

## 3. Conceito

`useMemo` permite armazenar em cache o resultado de uma função de cálculo entre renderizações, considerando suas dependências. Não deve ser adicionado a todo cálculo por padrão; meça ou identifique uma necessidade real antes de otimizar.

## 4. Demonstração do professor

```jsx
import { useMemo, useState } from "react";

function FilteredList({ items }) {
  const [query, setQuery] = useState("");

  const filteredItems = useMemo(() => {
    return items.filter((item) =>
      item.toLowerCase().includes(query.toLowerCase())
    );
  }, [items, query]);

  return (
    <section>
      <input value={query} onChange={(event) => setQuery(event.target.value)} />
      <ul>
        {filteredItems.map((item) => <li key={item}>{item}</li>)}
      </ul>
    </section>
  );
}
```

Explique que o resultado depende de `items` e `query`, e que o exemplo é principalmente ilustrativo: listas pequenas podem não precisar dessa otimização.

## 5. Reprodução do aluno

1. Crie uma lista de conceitos.
2. Adicione um campo de pesquisa.
3. Filtre a lista por texto.
4. Envolva o cálculo em `useMemo`.
5. Identifique as dependências usadas pelo cálculo.

## 6. Desafio prático

Adapte o filtro para considerar também uma categoria selecionada. Garanta que todas as dependências reativas usadas estejam na lista.

## 7. Erros comuns

- Acreditar que `useMemo` é necessário para a correção do filtro.
- Omitir dependências.
- Usar memoização para esconder problemas de arquitetura sem investigar a causa.
- Esperar que seja uma garantia semântica de que um valor nunca será recalculado.

## 8. Checklist

- [ ] Entendo qual resultado está sendo memoizado.
- [ ] Sei identificar dependências.
- [ ] Sei que a otimização deve ser justificada.

## 9. Próximo passo

Estude `useCallback`, que memoriza a identidade de uma função entre renderizações quando necessário.
