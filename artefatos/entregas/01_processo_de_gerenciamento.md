# **1. Descrição do Processo de Gerenciamento do Projeto**

## **1.1. Introdução**

Este documento descreve o processo de gerenciamento adotado para o desenvolvimento do projeto, conforme solicitado no Artefato 1. O gerenciamento foi realizado utilizando o método **Kanban**, integrado às boas práticas do PMBOK e inspirado nos princípios do Scrum para planejamento iterativo.

O controle das tarefas, o acompanhamento do progresso e a rastreabilidade das atividades foram executados por meio do **GitHub Projects**, ferramenta de gestão visual totalmente integrada ao repositório oficial do GitHub. Essa integração permite uma visão clara do fluxo de trabalho, reduz desperdícios e melhora a eficiência operacional.

---

## **1.2. Método de Gerenciamento Adotado**

O método de gerenciamento escolhido foi o **Kanban**, um sistema visual amplamente utilizado em métodos ágeis para controle contínuo de tarefas. Ele permite visualizar o estado atual do projeto, reduzir gargalos e manter o avanço progressivo das entregas.

O Kanban foi utilizado em conjunto com práticas inspiradas no **Scrum**, como:

- Definição e priorização de tarefas.
- Agrupamento das atividades em ciclos curtos.
- Monitoramento contínuo de progresso.

Essa combinação caracteriza uma abordagem **Scrumban**, totalmente alinhada às práticas adaptativas destacadas pelo PMBOK.

---

## **1.3. Estrutura do Quadro Kanban**

<!-- <img width="1920" height="1080" alt="Captura de tela 2025-10-23 212017" src="https://github.com/user-attachments/assets/9d5b4951-45d5-4288-af86-b0412df5b4f6" /> -->

https://github.com/user-attachments/assets/9d5b4951-45d5-4288-af86-b0412df5b4f6

O quadro Kanban foi criado no GitHub Projects e estruturado com as seguintes colunas, representando cada etapa do fluxo de trabalho:

### **1.3.1. Backlog**

Armazena todas as ideias, requisitos e tarefas iniciais ainda não selecionadas para execução.

### **1.3.2. Planejamento da Iteração (Sprint Atual)**

Inclui tarefas selecionadas e priorizadas para o ciclo atual de desenvolvimento.

### **1.3.3. Em Desenvolvimento**

Contém atividades em execução ativa, definidas com responsável e escopo claro.

### **1.3.4. Em Revisão/Testes**

Reúne atividades já desenvolvidas, mas que necessitam de avaliação, testes ou validação.

### **1.3.5. Concluído**

Armazena tarefas finalizadas e validadas pela equipe, encerrando o fluxo.

---

## **1.4. Descrição dos Cartões Criados**

A seguir, são apresentados exemplos dos cartões criados no quadro Kanban, contendo suas descrições e finalidades:

### **Cartão: "Documento de Visão e Escopo"**

- **Descrição:** Elaboração do artefato contendo objetivos, público-alvo e escopo inicial do sistema.
- **Status:** Em Desenvolvimento
- **Prioridade:** Alta

### **Cartão: "Histórias de Usuário"**

- **Descrição:** Levantamento dos requisitos funcionais em formato de histórias de usuário.
- **Status:** Planejamento da Iteração
- **Prioridade:** Alta

### **Cartão: "Especificação de Casos de Uso"**

- **Descrição:** Desenvolvimento do documento contendo atores, fluxos e cenários.
- **Status:** Backlog
- **Prioridade:** Média

### **Cartão: "Protótipo da Interface"**

- **Descrição:** Construção do protótipo visual da interface.
- **Status:** Backlog
- **Responsável:** Equipe

### **Cartão: "Documento de Arquitetura"**

- **Descrição:** Produção do architecture notebook conforme template fornecido.
- **Status:** Planejamento da Iteração

---

## **1.5. Integração com o GitHub e Controle de Versão**

O processo de gerenciamento fez uso extensivo das ferramentas integradas do **GitHub**, com destaque para o **GitHub Projects**, que funcionou como o núcleo da organização e acompanhamento do trabalho.

Diferentemente de ferramentas externas como Trello, Jira ou Asana, o GitHub Projects está **diretamente conectado ao sistema de controle de versão Git**, amplamente utilizado no mercado para desenvolvimento colaborativo. Essa integração elimina a necessidade de alternar entre múltiplas plataformas, reduzindo interrupções, distrações e a chamada _context switching_ — fenômeno estudado e documentado em pesquisas sobre produtividade em engenharia de software.

Além do quadro Kanban tradicional, o GitHub Projects oferece **múltiplas visualizações (views)** que ampliam a capacidade de análise e acompanhamento do progresso do projeto. Entre elas:

- **Board View (Kanban):** visualização principal para organização de tarefas em colunas.
- **Table View:** visão estruturada em tabela, permitindo filtros, ordenações e edição rápida.
- **Roadmap View:** representação de alto nível com entregas e milestones.
- **Chart View:** gráficos automáticos que mostram progresso, tarefas concluídas, tarefas abertas e distribuições por responsável ou prioridade.
- **Gantt-like Chart (Timeline):** visualização temporal que mostra dependências, duração estimada e sobreposição de tarefas, funcionando como um gráfico de Gantt moderno e nativo.

<!-- <img width="1774" height="770" alt="image" src="https://github.com/user-attachments/assets/fd2a4b25-a104-4491-8c7f-59a221f71939" /> -->

https://github.com/user-attachments/assets/fd2a4b25-a104-4491-8c7f-59a221f71939

Essas visualizações são fundamentais para o gerenciamento de projetos modernos, pois permitem alternar entre panoramas estratégicos (como o roadmap) e análises operacionais (como tabela e Kanban), tudo dentro do mesmo ecossistema.

Um estudo publicado por Meyer et al. (2017), no artigo **"Software Developers' Perceptions of Productivity"**, demonstra que alternar entre ferramentas distintas pode aumentar a carga cognitiva, elevar o tempo de retomada de foco e reduzir a eficiência geral das equipes. Manter ferramentas integradas em um único ecossistema — como GitHub + GitHub Projects — contribui de forma significativa para melhorar a fluidez do trabalho.

Dentro desse contexto, o projeto utilizou os seguintes recursos integrados:

- **GitHub Projects:** gestão de tarefas, quadro Kanban, roadmap e análise do progresso.
- **Issues e Cards:** cada tarefa é vinculada a um cartão e a uma issue correspondente.
- **Commits Referenciados:** cada entrega pode ser associada diretamente ao cartão/issue.
- **GitHub Actions:** automatização da geração de PDFs dos artefatos.

Essa integração fortalece as boas práticas do PMBOK, especialmente no que se refere ao controle de mudanças, rastreabilidade e unificação do fluxo de trabalho.

---

## **1.6. Conclusão**

O processo de gerenciamento adotado utilizou uma combinação das metodologias Kanban e Scrum, aplicadas dentro do ambiente integrado do GitHub. A estrutura organizada do quadro Kanban, as múltiplas visualizações fornecidas pelo GitHub Projects e a rastreabilidade ampliada pela integração com GitHub Actions contribuíram para um gerenciamento eficiente, visualmente claro e alinhado às práticas modernas de Engenharia de Software.

Este documento atende integralmente aos requisitos estabelecidos para o Artefato 1.
