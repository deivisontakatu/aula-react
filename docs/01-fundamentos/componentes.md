# Componentes

## 1. Objetivos de aprendizagem

- Definir componentes funcionais.
- Dividir uma interface em responsabilidades menores.
- Exportar e importar componentes.

## 2. O problema

Quando toda a interface fica em um único bloco de código, torna-se difícil localizar responsabilidades, reutilizar estruturas e fazer alterações com segurança.

## 3. Conceito

Um componente React é uma função JavaScript que retorna elementos React, geralmente descritos com JSX. Componentes podem compor outros componentes, formando uma árvore de interface. Por convenção, seus nomes começam com letra maiúscula.

## 4. Demonstração do professor

```jsx
function Cabecalho() {
  return <header><h1>React Lab</h1></header>;
}

function App() {
  return (
    <main>
      <Cabecalho />
      <p>Explore os conceitos do React.</p>
    </main>
  );
}

export default App;
```

Explique a diferença entre definir uma função de componente e utilizá-la como elemento JSX.

## 5. Reprodução do aluno

1. Identifique o cabeçalho de uma página como um componente.
2. Crie um componente `Cabecalho`.
3. Crie um componente `Rodape`.
4. Importe e use ambos em `App`.
5. Teste uma alteração em cada componente.

## 6. Desafio prático

Divida uma página de perfil em três componentes: cabeçalho, informações do perfil e rodapé. Evite criar componentes sem uma responsabilidade clara.

## 7. Erros comuns

- Nomear componentes com letra minúscula.
- Esquecer de exportar ou importar um componente.
- Definir componentes dentro de outros componentes sem necessidade, causando recriação da definição a cada renderização.
- Criar componentes muito grandes ou excessivamente fragmentados.

## 8. Checklist

- [ ] Sei criar um componente funcional.
- [ ] Consigo importar e reutilizar componentes.
- [ ] Consigo dividir uma interface em partes coerentes.

## 9. Próximo passo

Estude props para personalizar a saída de um componente com dados recebidos.
