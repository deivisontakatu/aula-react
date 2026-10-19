# JSX

## 1. Objetivos de aprendizagem

- Explicar o papel do JSX em componentes React.
- Inserir expressões JavaScript dentro da marcação.
- Reconhecer algumas diferenças entre JSX e HTML.

## 2. O problema

Criar elementos de interface por meio de chamadas extensas de funções pode tornar a estrutura visual difícil de ler. JSX permite descrever essa estrutura de forma próxima à marcação HTML, combinada com JavaScript.

## 3. Conceito

JSX é uma extensão de sintaxe para JavaScript usada com frequência no React. Ela é transformada pela ferramenta de build em chamadas que descrevem elementos React. JSX não é HTML literal, embora sua aparência seja semelhante.

Expressões JavaScript podem ser inseridas entre chaves, por exemplo `{nome}`. Atributos seguem convenções próprias, como `className` no lugar de `class`.

## 4. Demonstração do professor

Apresente um componente que exibe um título, uma variável e o resultado de uma expressão simples. Mostre o que acontece quando a expressão muda.

```jsx
function Saudacao() {
  const nome = "Ana";

  return (
    <section>
      <h1>Olá, {nome}!</h1>
      <p>Bem-vinda ao React.</p>
    </section>
  );
}
```

Explique que o JSX retornado descreve a interface a ser renderizada.

## 5. Reprodução do aluno

1. Crie um componente de apresentação pessoal.
2. Declare variáveis para nome e curso.
3. Mostre os valores usando chaves no JSX.
4. Acrescente uma expressão JavaScript simples.
5. Altere os valores e observe a saída.

## 6. Desafio prático

Crie um pequeno cartão de perfil com nome, curso e ano de ingresso. Exiba uma mensagem que dependa de uma variável.

## 7. Erros comuns

- Usar `class` em vez de `className` no JSX.
- Tentar inserir instruções completas, como `if`, diretamente dentro de uma expressão JSX.
- Retornar vários elementos irmãos sem agrupá-los em um elemento pai ou fragmento.
- Esquecer as chaves ao inserir uma expressão JavaScript.

## 8. Checklist

- [ ] Consigo identificar JSX.
- [ ] Sei inserir variáveis com chaves.
- [ ] Conheço diferenças básicas entre JSX e HTML.

## 9. Próximo passo

Use JSX dentro de componentes, unidades reutilizáveis da interface.
