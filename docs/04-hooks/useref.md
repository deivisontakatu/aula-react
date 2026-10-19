# useRef

## 1. Objetivos de aprendizagem

- Explicar a finalidade de `useRef`.
- Utilizar uma referência a um elemento DOM.
- Diferenciar uma referência de estado.

## 2. O problema

Às vezes, precisamos acessar um elemento do DOM, como focar um campo, ou guardar um valor entre renderizações sem que sua alteração provoque uma nova renderização.

## 3. Conceito

`useRef` retorna um objeto cuja propriedade `current` pode guardar um valor mutável entre renderizações. Alterar `current` não solicita uma nova renderização. Para valores que precisam atualizar o que aparece na tela, prefira estado.

## 4. Demonstração do professor

```jsx
import { useRef } from "react";

function SearchBox() {
  const inputRef = useRef(null);

  function focusInput() {
    inputRef.current?.focus();
  }

  return (
    <div>
      <input ref={inputRef} aria-label="Pesquisar conceitos" />
      <button onClick={focusInput}>Focar pesquisa</button>
    </div>
  );
}
```

Explique a ligação entre `ref` e o elemento DOM.

## 5. Reprodução do aluno

1. Crie uma referência com `useRef(null)`.
2. Associe a referência ao campo de texto.
3. Crie um botão que chame `focus()`.
4. Teste a interação.

## 6. Desafio prático

Adicione um botão que coloque o foco no campo de pesquisa quando a pessoa clicar nele.

## 7. Erros comuns

- Usar uma ref quando o valor deveria atualizar a interface.
- Ler ou alterar referências durante a renderização sem uma razão apropriada.
- Supor que a ref já contém o elemento antes de ele ser associado.

## 8. Checklist

- [ ] Sei criar uma referência.
- [ ] Consigo acessar um elemento DOM com `ref`.
- [ ] Entendo que alterar `current` não provoca renderização.

## 9. Próximo passo

Conheça técnicas de memoização e saiba quando uma otimização é realmente necessária.
