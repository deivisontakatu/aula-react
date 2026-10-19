# React Router

## 1. Objetivos de aprendizagem

- Explicar a necessidade de roteamento no lado do cliente.
- Reconhecer rotas e links de navegação.
- Planejar uma tela de catálogo e uma tela de detalhes.

## 2. O problema

Aplicações com mais de uma tela precisam permitir que a pessoa navegue entre páginas, compartilhe endereços e use os controles de voltar e avançar do navegador.

## 3. Conceito

React Router é uma biblioteca popular de roteamento para React. Ela permite associar caminhos da URL a componentes e navegar entre rotas. A configuração exata depende do modo de uso e da versão da biblioteca.

## 4. Demonstração do professor

Apresente um exemplo pequeno com uma rota de início e outra de detalhes. Explique os conceitos de rota, link e parâmetro. Antes de executar um exemplo completo, confirme a sintaxe adequada à versão instalada.

```jsx
import { BrowserRouter, Routes, Route, Link } from "react-router-dom";

function Home() {
  return <h1>Catálogo de conceitos</h1>;
}

function About() {
  return <h1>Sobre o React Lab</h1>;
}

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Início</Link>
        <Link to="/sobre">Sobre</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/sobre" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

## 5. Reprodução do aluno

1. Identifique as telas de uma aplicação.
2. Defina um caminho para cada tela.
3. Configure as rotas.
4. Crie links para navegar entre as telas.
5. Teste navegação, voltar e avançar.

## 6. Desafio prático

Projete rotas para uma página inicial e uma página de detalhes de conceito. Descreva como o identificador do conceito poderá ser recebido pela rota.

## 7. Erros comuns

- Esquecer de configurar o roteador.
- Usar links comuns de navegação quando a intenção é navegar por rotas do cliente sem recarregar toda a página.
- Confundir um caminho da URL com o nome de um componente.
- Copiar exemplos de versões diferentes sem verificar a documentação.

## 8. Checklist

- [ ] Entendo o papel do roteamento.
- [ ] Sei diferenciar rota e link.
- [ ] Consigo planejar uma navegação entre telas.

## 9. Próximo passo

Conecte a interface a uma API para receber dados externos.
