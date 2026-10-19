# Virtual DOM e reconciliação

## 1. Objetivos de aprendizagem

- Explicar de forma introdutória o que representa o Virtual DOM.
- Entender a ideia de reconciliação.
- Evitar simplificações incorretas sobre desempenho.

## 2. O problema

Uma aplicação interativa precisa manter a interface alinhada aos dados e ao estado. Alterar diretamente cada elemento manualmente pode espalhar lógica de atualização pelo código.

## 3. Conceito

O termo Virtual DOM é usado para descrever representações em memória da interface. O React compara a descrição anterior com a nova durante a reconciliação e determina quais atualizações são necessárias para manter a interface sincronizada. Os detalhes internos variam conforme o tipo de renderização e a implementação do React.

É importante não interpretar isso como uma garantia de que React será sempre mais rápido. O benefício central para quem desenvolve é declarar a interface e deixar o React coordenar as atualizações.

## 4. Demonstração do professor

Use um exemplo de contador. Explique a sequência: o estado muda, o componente é renderizado novamente, o React reconcilia a nova descrição com a anterior e as alterações necessárias são refletidas na interface.

Desenhe a sequência no quadro:

`interação → atualização do estado → renderização → reconciliação → atualização da interface`

## 5. Reprodução do aluno

1. Observe um componente com um valor inicial.
2. Identifique a interação que muda o estado.
3. Descreva quais partes da interface dependem desse valor.
4. Explique a sequência de atualização sem afirmar que a página inteira é reconstruída do zero.

## 6. Desafio prático

Escreva uma explicação de até cinco frases para um colega iniciante sobre o que ocorre depois de clicar em um botão que altera o estado.

## 7. Erros comuns

- Dizer que o Virtual DOM é uma cópia completa e permanentemente idêntica do DOM do navegador.
- Afirmar que o React nunca atualiza partes já existentes do DOM.
- Tratar o Virtual DOM como uma garantia automática de desempenho.
- Confundir renderização de um componente com reconstrução integral da página.

## 8. Checklist

- [ ] Entendo a ideia geral de reconciliação.
- [ ] Sei descrever a sequência de atualização.
- [ ] Consigo explicar o conceito sem prometer ganhos automáticos de desempenho.

## 9. Próximo passo

Aprenda a passar dados para componentes por meio de props.
