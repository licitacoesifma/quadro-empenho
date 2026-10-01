# 📄 Gerador de Quadro de Empenho

Uma aplicação web interativa e responsiva desenvolvida para facilitar, padronizar e automatizar a criação de **Quadros de Empenho**. O sistema permite que o usuário preencha um formulário intuitivo, visualize o documento em tempo real (Live Preview) e exporte o resultado final em um arquivo PDF perfeitamente formatado, seguindo padrões de documentos oficiais.

![Status do Projeto](https://img.shields.io/badge/Status-Concluído-success)
![Linguagem](https://img.shields.io/badge/Linguagem-JavaScript_|_HTML_|_CSS-yellow)
![Framework](https://img.shields.io/badge/Framework-Tailwind_CSS-38B2AC)

---

## ✨ Funcionalidades

* **Formulário Dinâmico e Tipado:** Campos estruturados para informações básicas, dados da licitação/contrato e itens a serem executados.
* **Cálculo Automático:** Multiplicação instantânea de *Quantidade (Inteiro)* x *Valor Unitário*, além do cálculo do *Valor Total Geral*.
* **Gerenciamento Inteligente de Itens:** 
  * Adição e remoção dinâmica de itens.
  * Renumeração automática (se o item 2 é removido, o 3 vira 2).
  * O campo de quantidade aceita apenas números inteiros.
* **Live Preview Opcional:** Um modo de visualização em tempo real. Ao ser ativado, a tela se divide e exibe uma simulação exata de como a página A4 ficará, atualizando a cada tecla digitada.
* **Exportação para PDF:** Geração de documento PDF no formato A4, com tabelas detalhadas, células mescladas (*colspans* estruturados) e numeração de página, utilizando as bibliotecas `jsPDF` e `jsPDF-AutoTable`.
* **Design UI/UX Profissional:** Interface limpa e moderna construída com Tailwind CSS, totalmente responsiva (funciona perfeitamente em celulares, tablets e desktops).
* **Toast Notifications:** Alertas visuais discretos e elegantes para feedbacks de sucesso ("PDF gerado") ou erros.

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído focado em ser leve e rodar diretamente no navegador da máquina do cliente, sem necessidade de back-end.

* **HTML5** & **CSS3**
* **Vanilla JavaScript** (Sem frameworks JS complexos para a lógica de negócio)
* **[Tailwind CSS](https://tailwindcss.com/)** (Carregado via CDN para estilização rápida e responsiva)
* **[jsPDF](https://github.com/parallax/jsPDF)** (Para a criação da estrutura base do PDF)
* **[jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable)** (Plugin para renderização perfeita das grades/tabelas dentro do PDF)

---

## 🚀 Como Executar o Projeto

Como o projeto não possui dependências de build (como Node.js, Webpack ou Vite), executá-lo é extremamente simples.

1. **Faça o clone do repositório:**
   ```bash
   git clone https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git
   ```
2. **Navegue até a pasta do projeto:**
   ```bash
   cd NOME_DO_REPOSITORIO
   ```
3. **Abra o arquivo no navegador:**
   Basta dar um duplo clique no arquivo `index.html` ou arrastá-lo para dentro do seu navegador de preferência (Chrome, Edge, Firefox, etc).

---

## 💻 Estrutura do Código

A aplicação foi concentrada no modelo *Single Page* para facilidade de distribuição (um único arquivo `index.html`), dividido internamente nas seguintes seções:

* `<head>`: Importação do Tailwind CSS, Fontes (Google Fonts - *Inter*) e bibliotecas jsPDF. Definição de estilos customizados para barras de rolagem e simulação da folha A4.
* `<body>`:
  * **Header:** Barra superior com o título, botão de ativar Preview e botão de Exportar PDF.
  * **Formulário (Esquerda):** Cards separados por contexto (Informações Básicas, Licitação e Itens).
  * **Live Preview (Direita):** Container que renderiza o layout visual do documento A4. Oculto por padrão.
* `<script>`:
  * Lógica de UI (Toasts, Toggle do Preview).
  * Lógica de negócio (Cálculos matemáticos, manipulação do DOM para adicionar/remover itens, máscaras/formatação de moeda).
  * Sincronização em tempo real (Event listeners escutando inputs).
  * Exportação `gerarPDF()` configurando os eixos X e Y das tabelas no jsPDF.

---

## 📝 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usá-lo e modificá-lo conforme necessário.