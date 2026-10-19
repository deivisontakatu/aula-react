# useEffect

## 1. Objetivos de aprendizagem

- Explicar o propósito de `useEffect`.
- Entender a lista de dependências.
- Reconhecer quando um efeito precisa de limpeza.

## 2. O problema

Um componente às vezes precisa sincronizar-se com algo externo ao React, como uma assinatura de eventos, um temporizador, uma conexão ou uma API. Esse tipo de trabalho exige cuidado com o início, as atualizações e a limpeza.

## 3. Conceito

`useEffect` permite sincronizar um componente com sistemas externos. O efeito é declarado como uma função; opcionalmente, ela pode retornar outra função para limpar recursos antes de uma nova execução ou quando o componente deixa de ser utilizado. As dependências indicam os valores reativos dos quais o efeito depende.

Não use `useEffect` automaticamente para todo cálculo ou transformação de dados. Quando um valor pode ser calculado durante a renderização a partir de props e estado, muitas vezes não é necessário armazená-lo ou sincronizá-lo por meio de um efeito.

## 4. Demonstração do professor

```jsx
import { useEffect, useState } from "react";

function WindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    function updateWidth() {
      setWidth(window.innerWidth);
    }

    window.addEventListener("resize", updateWidth);
    return () => window.removeEventListener("resize", updateWidth);
  }, []);

  return <p>Largura da janela: {width}px</p>;
}
```

Explique a assinatura do evento, a função de limpeza e por que a dependência está vazia neste exemplo. Este exemplo pressupõe execução no navegador.

## 5. Reprodução do aluno

1. Crie um componente que mostre uma informação sincronizada com o navegador.
2. Registre um evento dentro de um efeito.
3. Atualize o estado quando o evento ocorrer.
4. Retorne uma função de limpeza.
5. Verifique que o ouvinte é removido ao desmontar o componente.

## 6. Desafio prático

Crie um temporizador que seja iniciado quando um componente aparece e limpo quando ele deixa de ser exibido.

## 7. Erros comuns

- Omitir dependências reativas necessárias.
- Usar efeitos para cálculos que podem ser feitos durante a renderização.
- Esquecer a limpeza de assinaturas ou temporizadores.
- Tratar `useEffect` como um equivalente universal a todos os métodos de ciclo de vida de classes.

## 8. Checklist

- [ ] Entendo para que serve um efeito.
- [ ] Sei interpretar a lista de dependências.
- [ ] Consigo limpar um recurso externo.

## 9. Próximo passo

Use `useRef` quando precisar manter uma referência mutável ou acessar um elemento do DOM sem provocar renderização.
