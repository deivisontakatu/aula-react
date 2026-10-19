# Aula 11 — React Router

## Objetivos de aprendizagem

Compreender a função do roteamento em aplicações React, diferenciar caminhos de URL de componentes e reconhecer os principais elementos de uma navegação por rotas.

## 1. Por que precisamos de roteamento?

Uma aplicação pode ter várias telas: página inicial, catálogo, detalhes de um conceito, formulário e página de informações. O roteamento associa caminhos da URL às partes da interface que devem ser exibidas.

Sem uma estratégia de navegação, a lógica para alternar entre telas pode ficar espalhada por vários componentes.

## 2. O que é React Router?

React Router é uma biblioteca de roteamento bastante utilizada no ecossistema React. Ela oferece recursos para associar URLs a componentes e navegar entre páginas.

A configuração exata depende da versão e do modo de utilização da biblioteca. Por isso, exemplos devem ser conferidos com a documentação da versão adotada no curso.

## 3. Conceitos fundamentais

- **Rota:** regra que associa um caminho a uma interface.
- **URL:** endereço que identifica a localização atual.
- **Link:** elemento de navegação entre rotas.
- **Parâmetro de rota:** parte variável do caminho, como o identificador de um conceito.
- **Rota aninhada:** rota organizada dentro de uma estrutura de rotas pai.
- **Página não encontrada:** estado apresentado quando nenhum caminho conhecido corresponde à URL.

## 4. Exemplo conceitual

Imagine um catálogo chamado React Lab. Ele pode ter os caminhos:

| Caminho | Conteúdo |
|---|---|
| / | Página inicial |
| /conceitos | Lista de conceitos |
| /conceitos/jsx | Detalhes sobre JSX |
| /sobre | Informações sobre o projeto |

A rota de detalhes pode usar um parâmetro, por exemplo /conceitos/:id, para representar diferentes conceitos com a mesma estrutura de página.

## 5. Navegação sem recarga completa

Links de roteamento permitem mudar a rota da aplicação sem depender de uma navegação tradicional que recarregue todo o documento a cada clique. O roteador atualiza a interface conforme a URL e a configuração de rotas.

Isso não elimina a necessidade de pensar no carregamento inicial, no acesso direto a uma URL e na configuração do servidor para aplicações de página única.

## 6. URL e estado da aplicação

Informações importantes para navegação, como a página atual, filtros compartilháveis ou identificadores de recursos, podem ser representadas na URL. Isso facilita compartilhar links e usar os controles voltar e avançar do navegador.

Nem todo estado precisa estar na URL. A decisão depende de a informação precisar ser compartilhada, marcada como favorita ou preservada ao recarregar a página.

## 7. Boas práticas

- Escolha caminhos claros e consistentes.
- Use links semânticos para navegação.
- Planeje o comportamento de rotas inexistentes.
- Pense no acesso direto a páginas internas.
- Consulte a documentação da versão instalada.
- Considere acessibilidade, foco e títulos ao mudar de página.

## 8. Erros comuns

- Confundir o nome de um componente com o caminho da rota.
- Configurar rotas sem pensar no acesso direto pela URL.
- Usar elementos de navegação inadequados.
- Copiar exemplos de versões diferentes da biblioteca.
- Colocar toda a lógica de navegação dentro de um único componente sem organização.

## Resumo

React Router ajuda a organizar a navegação entre telas e a associar URLs a componentes. Um bom roteamento torna a aplicação mais previsível, facilita o compartilhamento de links e melhora a experiência de navegação.

## Para refletir

1. Qual problema uma biblioteca de roteamento resolve?
2. Qual é a diferença entre rota e link?
3. Quando faz sentido colocar um identificador na URL?
4. Por que é importante testar o acesso direto a uma rota?

## Referências

- [Documentação oficial do React Router](https://reactrouter.com/)
- [React Router — Tutorial](https://reactrouter.com/start/declarative/installation)
