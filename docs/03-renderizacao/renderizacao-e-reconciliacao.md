# Renderização e reconciliação

## 1. Objetivos de aprendizagem

- Diferenciar renderização de atualização do DOM.
- Reconhecer situações que podem provocar uma nova renderização.
- Entender a relação entre identidade dos componentes, estado e reconciliação.

## 2. O problema

Quando dados mudam, é importante compreender como a interface passa de uma descrição para outra e por que a posição ou identidade de um componente pode afetar a preservação do estado.

## 3. Conceito

Em termos introdutórios, a renderização do React significa executar componentes para calcular a descrição da interface. Em seguida, o React reconcilia essa descrição com a anterior e aplica as mudanças necessárias. Uma renderização não significa, necessariamente, que todos os elementos do DOM sejam recriados.

O tipo e a posição de um componente na árvore, assim como suas chaves, ajudam o React a determinar se o estado existente deve ser preservado ou se uma nova identidade deve ser criada.

## 4. Demonstração do professor

Use um componente com estado e um componente pai que atualiza outro valor. Observe que uma renderização pode ocorrer sem que todo o DOM seja substituído. Depois, demonstre como uma `key` diferente pode reiniciar o estado de um componente.

## 5. Reprodução do aluno

1. Crie um componente com um contador interno.
2. Faça o componente pai atualizar outro estado.
3. Observe o comportamento do componente filho.
4. Altere a chave do componente de forma controlada e observe o reinício do estado.

## 6. Desafio prático

Explique a diferença entre renderizar novamente um componente e recriar a página inteira. Inclua um exemplo da aplicação prática de uma `key`.

## 7. Erros comuns

- Achar que toda renderização altera necessariamente o DOM.
- Usar `key` como um truque geral de desempenho.
- Ignorar o efeito da identidade e da posição na preservação do estado.

## 8. Checklist

- [ ] Diferencio renderização e atualização do DOM.
- [ ] Entendo a finalidade da reconciliação.
- [ ] Reconheço como a identidade afeta o estado.

## 9. Próximo passo

Estude `useEffect` para sincronizar um componente com sistemas externos.
