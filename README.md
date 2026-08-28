# pesquisa-opiniao-simulador
Plataforma demonstrativa e privada de pesquisa de opinião pública informatizada (HTML5/CSS3/JS/Firebase).
# 📊 Plataforma de Pesquisa de Opinião Informatizada

> **Aviso Legal / Disclaimer:**  
> Este projeto é um protótipo estritamente demonstrativo, educacional e de uso privado/doméstico. Ele **não** possui qualquer vínculo com o Tribunal Superior Eleitoral (TSE) ou com a Justiça Eleitoral brasileira. Não se destina à publicação de pesquisas eleitorais públicas sem o devido registro legal (Lei nº 9.504/1997).

---

## 📌 Visão Geral do Sistema

A **Plataforma de Pesquisa de Opinião Informatizada** é uma aplicação web leve, moderna e responsiva desenvolvida para simulação e coleta anônima de dados estatísticos de intenção de voto em ambiente privado. 

### 🚀 Principais Recursos
* **Layout Adaptável e Temas:** Suporte nativo aos modos Claro e Escuro (`data-theme="dark"` / `data-theme="light"`).
* **Menu Deslizante (Drawer Menu):** Navegação lateral fluida para acesso rápido a instruções e suporte técnico.
* **Apex Counter Module:** Contador de acessos determinístico (global e local) que roda 100% no cliente sem dependência de APIs externas (imune a erros 404/410).
* **Anonimato de Dados:** Processamento de respostas sem coleta de dados pessoais, em conformidade com as diretrizes da LGPD.
* **Painel de Gestão e Auditoria:** Exibição de estatísticas parciais em tempo real, exportação de backup em formato JSON e redefinição de amostragem.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5:** Estrutura semântica e acessível.
* **CSS3 Custom Properties:** Estilização modular com variáveis globais para alternância de temas.
* **JavaScript ES6+:** Manipulação dinâmica de DOM, estado do sistema e manipulação de arquivos localmente.

---

## 📖 Estrutura do Código e Mapeamento de Funções

### 1. Variáveis e Estados Globais
* `candidatos`: Array de objetos que armazena a lista de opções e a contagem de votos.
  * Estrutura: `{ id: '01', nome: 'Candidato A', votos: 0 }`
* `selecionado`: Variável de controle que guarda a opção marcada pelo usuário no momento da votação.

### 2. Funções do Sistema (JavaScript)
* `toggleTheme()`: Alterna a propriedade `data-theme` do elemento `<html>` entre `dark` e `light`.
* `toggleDrawer()`: Ativa ou desativa a classe `active` do menu lateral (`#drawerMenu`).
* `initApexCounter(config)`: Inicializa o contador determinístico de acessos locais e simulados.
  * *Configuração utilizada:* `storageKey: 'pesquisa_opiniao_v1'`, `baseValue: 1250`, `growthRate: 18`, `startDate: '2026-01-01'`.
* `renderCandidatos()`: Atualiza dinamicamente a interface da pesquisa na DOM (`#candidatesList`).
* `selecionar(id)`: Define a opção marcada pelo usuário.
* `limparSelecao()`: Reseta a escolha atual sem contabilizar voto.
* `registrarVoto()`: Incrementa o contador da opção selecionada e exibe confirmação.
* `renderAnalytics()`: Calcula e exibe o percentual e total de votos no painel administrativo (`#analyticsPanel`).
* `exportarBackup()`: Gera e faz o download automático do arquivo `pesquisa_backup.json`.
* `resetarDados()`: Limpa os dados de contagem da amostra local após confirmação.

---

## 📂 Estrutura de Arquivos no Repositório

```text
/ (Raiz do repositório)
├── index.html        # Interface completa (HTML, CSS e JavaScript unificados)
└── README.md         # Documentação técnica e guia de uso do projeto
