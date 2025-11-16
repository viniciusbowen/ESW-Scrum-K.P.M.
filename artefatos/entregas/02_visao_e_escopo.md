# Sistema de Gestão Ágil

## Artefato 2 – Documento de Visão e Escopo

---

## 1\. Introdução

Este documento apresenta a visão e o escopo de um sistema para apoiar o gerenciamento de projetos ágeis inspirado no framework Scrum. O objetivo é oferecer um artefato de comunicação entre equipe, stakeholders e avaliadores, definindo o problema tratado, as necessidades dos usuários e a solução proposta em alto nível.

## 2\. Posicionamento

### 2.1 Declaração do Problema

O problema de organizar e gerenciar projetos ágeis de forma integrada e colaborativa afeta equipes de desenvolvimento, Product Owners, Scrum Masters e gestores de projeto; o impacto desse problema inclui perda de produtividade, falhas de comunicação, retrabalho e falta de rastreabilidade das entregas. Uma solução bem-sucedida deve aumentar a transparência do progresso, reduzir o retrabalho, melhorar a comunicação entre papéis e permitir decisões mais rápidas e informadas.

### 2.2 Declaração de Posicionamento do Produto

Para equipes de desenvolvimento e gestores que adotam metodologias ágeis e precisam gerenciar backlog, planejar sprints e acompanhar entregas de forma colaborativa, o ScrumTrack é um sistema de gestão para processos Scrum que fornece controle estruturado do ciclo (histórias, backlog, sprints, tarefas e incrementos). Ao contrário de planilhas e ferramentas genéricas, o ScrumTrack é específico para o Scrum, integrando os papéis, cerimônias e artefatos do framework com uma interface simples e recursos de colaboração.

## 3\. Descrição das Partes Interessadas

### 3.1 Resumo das Partes Interessadas

| Nome                     | Descrição                                                             | Responsabilidades                                                                           |
| :----------------------- | :-------------------------------------------------------------------- | :------------------------------------------------------------------------------------------ |
| Product Owner (PO)       | Representante do cliente/produto responsável por priorizar o trabalho | Definir e priorizar o backlog do produto, aceitar entregas e determinar objetivos da sprint |
| Scrum Master (SM)        | Facilitador do processo Scrum na equipe                               | Remover impedimentos, garantir que o processo Scrum seja seguido e facilitar cerimônias     |
| Desenvolvedor (Dev)      | Membro técnico que implementa funcionalidades                         | Implementar histórias, estimar esforço, atualizar status de tarefas                         |
| Cliente / Usuário Final  | Beneficiário do produto final                                         | Fornecer requisitos e feedback, validar incrementos entregues                               |
| Administrador do Sistema | Responsável pela operação e manutenção da plataforma                  | Gerenciar usuários, permissões, backups e disponibilidade do sistema                        |

### 3.2 Ambiente de Trabalho dos Usuários

Os usuários utilizarão o ScrumTrack em estações de trabalho conectadas à internet (desktop ou laptop) e em navegadores modernos (Chrome, Firefox, Edge). As equipes típicas têm entre 3 e 10 membros por projeto. O ciclo de trabalho segue sprints de 1 a 4 semanas com atividades de planejamento, execução e revisão. Espera-se integração opcional com sistemas de controle de versão (por exemplo, GitHub/GitLab) e ferramentas de comunicação (por exemplo, Slack, Microsoft Teams).

## 4\. Visão Geral do Produto

### 4.1 Necessidades e Funcionalidades

O quadro a seguir apresenta, em alto nível, as necessidades dos stakeholders, a prioridade e as funcionalidades previstas por versão planejada.

| Necessidade                                  | Prioridade | Funcionalidade                                                          | Lançamento Planejado |
| :------------------------------------------- | ---------: | :---------------------------------------------------------------------- | :------------------- |
| Autenticação e controle de acesso por papéis |       Alta | Registro, login, recuperação de senha, controle de papéis (PO, SM, Dev) | 1.0                  |
| Gerenciar projetos e equipes                 |       Alta | CRUD de projetos, atribuição de membros e papéis                        | 1.0                  |
| Gerenciar backlog de produto e de sprint     |       Alta | CRUD de histórias de usuário, priorização e ordenação do backlog        | 1.0                  |
| Planejamento e acompanhamento de sprint      |       Alta | Criar plano de sprint (objetivo, trabalho, equipe, tarefas, increment)  | 1.0                  |
| Visualização do progresso                    |      Média | Dashboard, status de tarefas, quadro kanban e burndown chart            | 1.1                  |
| Comunicação e comentários                    |      Baixa | Comentários em histórias/tarefas e notificações básicas                 | 1.2                  |

## 5\. Outros Requisitos do Produto

Requisitos de alto nível relativos a padrões, desempenho, segurança e documentação:

| Requisito                        | Prioridade | Observações                                                                                          |
| :------------------------------- | ---------: | :--------------------------------------------------------------------------------------------------- |
| Usabilidade                      |       Alta | Interface responsiva e intuitiva; suporte a acessibilidade básica (contraste, navegação por teclado) |
| Desempenho                       |       Alta | Resposta a ações do usuário em menos de 2 segundos em condições normais                              |
| Segurança                        |       Alta | Armazenamento seguro de credenciais (hash), comunicação via TLS, controle de autorização por papéis  |
| Confiabilidade / Disponibilidade |      Média | Meta de disponibilidade mínima de 99% em ambiente de produção                                        |
| Conformidade                     |       Alta | Aderência à LGPD quanto a coleta, armazenamento e eliminação de dados pessoais                       |
| Portabilidade                    |       Alta | Compatibilidade com navegadores modernos; arquiteturas de backend compatíveis com Linux/Windows      |
| Documentação                     |      Média | Manuais de usuário, guia de instalação e documentação para administradores                           |

Assunções / restrições: integrações com ferramentas externas serão realizadas via APIs públicas quando disponíveis; opções de implantação incluem hospedagem em nuvem ou infraestrutura institucional, escolhidas conforme critérios de custo, segurança e disponibilidade.

## 6\. Elementos da Solução Proposta

Resumo técnico e arquitetural de alto nível:

- Arquitetura: aplicação web organizada em camadas (apresentação, lógica de negócio e persistência). A escolha entre arquitetura monolítica ou modular deverá considerar requisitos de escalabilidade, manutenção e integração.
- Componentes principais: módulo de autenticação e controle de acesso, serviço de gestão de projetos e backlog, módulo para planejamento e acompanhamento de sprints, interface web de acompanhamento e camada de persistência.
- Impacto de ferramentas: recomenda-se priorizar ferramentas consolidadas e de código aberto para reduzir riscos e acelerar entrega; a seleção final deve ponderar comunidade, suporte, curva de adoção e requisitos operacionais.
- Manutenção e operação: implantação em ambiente gerenciado ou em infraestrutura institucional com monitoramento (logs e métricas), política de backup e planos de recuperação.
