# Especificação de Requisitos Funcionais — Histórias de Usuário

Este documento lista as histórias de usuário que descrevem os requisitos funcionais do sistema sob a perspectiva do usuário final. Cada história segue o formato:

**Como** \< quem\> **Eu quero** \<o quê\>

**Para** \<porquê/benefício\> Para cada história há critérios de aceitação e prioridade.

---

## HU-01 — Autenticação de usuário

**Como** usuário do sistema  
**Eu quero** poder criar uma conta e fazer login com credenciais seguras  
**Para** acessar os serviços do sistema e proteger meus dados

Critérios de aceitação:

- O usuário consegue se registrar com e-mail e senha.  
- O sistema valida o e-mail e exige senha com tamanho mínimo.  
- O usuário consegue efetuar login com e-mail e senha válidos.  
- O sistema oferece recuperação de senha via e-mail.

---

## HU-02 — Controle de papéis e permissões

**Como** administrador do sistema  
**Eu quero** atribuir papéis (Proprietário do Produto, Scrum Master, Desenvolvedor) aos usuários  
**Para** garantir que cada usuário acesse apenas as funcionalidades permitidas ao seu papel

Critérios de aceitação: O administrador pode atribuir papéis diferentes a cada usuário em cada projeto. O sistema impede que usuários sem permissão acessem funções restritas ao seu papel. Mudanças de papel são registradas para auditoria.

---

## HU-03 — Criar e gerenciar projetos

**Como** membro da organização  
**Eu quero** criar projetos e atribuir membros à equipe do projeto  
**Para** organizar o trabalho por contexto de produto/projeto

Critérios de aceitação:

- O usuário com permissão cria um projeto com nome e descrição.  
    
- É possível adicionar e remover membros do projeto com papéis.  
    
- O projeto aparece na lista de projetos do usuário.  
    
- Um usuário pode integrar múltiplos projetos e visualizar a lista de projetos dos quais participa.

---

## HU-04 — Registrar histórias de usuário (backlog do produto)

**Como** Product Owner  
**Eu quero** criar, editar, ordenar e priorizar histórias de usuário no backlog do produto  
**Para** manter o backlog organizado e refletir as prioridades do produto

Critérios de aceitação:

- O PO consegue criar uma história com título, descrição, story points (opcional) e critérios de aceitação.  
- O PO consegue editar e excluir histórias.  
- O PO consegue ordenar/priorizar histórias no backlog.

---

## HU-05 — Planejar sprint (plano de sprint)

**Como** Product Owner ou Scrum Master  
**Eu quero** criar um plano de sprint que contenha objetivo, equipe, tarefas e backlog selecionado  
**Para** formalizar o trabalho a ser entregue durante a sprint

Critérios de aceitação:

- É possível definir o objetivo da sprint (what).  
- É possível selecionar histórias/tarefas do backlog para compor a sprint (how/backlog).  
- É possível indicar a equipe responsável (who) e descrever o incremento esperado (increment).

---

## HU-06 — Gerenciar tarefas do sprint

**Como** Desenvolvedor  
**Eu quero** criar, atribuir, atualizar status e comentar tarefas dentro do plano de sprint  
**Para** organizar o trabalho diário e reportar progresso

Critérios de aceitação:

- Desenvolvedores conseguem criar subtarefas vinculadas a uma história.  
- Tarefas possuem status (ex.: To Do, Doing, Done) e podem ser movidas entre estados.  
- É possível atribuir tarefa a um membro da equipe.  
- É possível adicionar comentários às tarefas.

---

## HU-07 — Quadro Kanban / Visualização do Sprint

**Como** membro da equipe  
**Eu quero** visualizar as tarefas do sprint em um quadro (colunas por status)  
**Para** acompanhar o progresso de forma visual e identificar impedimentos

Critérios de aceitação:

- O quadro exibe tarefas organizadas por colunas de status.  
- Arrastar e soltar uma tarefa altera seu status.  
- O quadro atualiza o indicador de responsável e prazo exibido na tarefa.

---

## HU-08 — Dashboard e relatórios simples

**Como** Sponsor / Gerente  
**Eu quero** ver um resumo do progresso (número de tarefas abertas/fechadas, sprint atual) em um painel  
**Para** avaliar rapidamente o estado do projeto e apoiar decisões de gestão

Critérios de aceitação:

- O dashboard apresenta contadores de tarefas por status e sprint ativo.  
- Disponibiliza gráficos simples (ex.: progresso por sprint, lista de impedimentos).

---

## HU-09 — Notificações e comentários

**Como** membro da equipe  
**Eu quero** receber notificações sobre mudanças relevantes (atribuição, comentários) e poder comentar itens  
**Para** ser informado sobre atualizações que me afetam e colaborar com a equipe

Critérios de aceitação:

- O usuário recebe notificações dentro da interface quando for mencionado ou quando tarefa for atribuída.  
- O usuário pode adicionar comentários em histórias e tarefas; comentários exibem autor e timestamp.

---

## HU-11 — Gerenciar backlog de sprint

**Como** Product Owner ou Scrum Master  
**Eu quero** criar, editar e remover itens do backlog de sprint  
**Para** ajustar o conteúdo da sprint conforme necessidade e rastrear o trabalho associado

Critérios de aceitação:

- É possível adicionar itens de backlog ao backlog de sprint com título, descrição e estimativa.  
- Itens do backlog de sprint podem ser editados e excluídos por usuários com permissão.  
- Itens do backlog de sprint aparecem vinculados ao plano de sprint correspondente.

---

## HU-10 — Exportar e salvar registros do sprint

**Como** Administrador / PO  
**Eu quero** exportar o plano de sprint e o backlog em formato legível (CSV/PDF)  
**Para** arquivar decisões e resultados das sprints

Critérios de aceitação:

- É possível exportar backlog e plano de sprint em CSV e PDF.  
- O export inclui campos essenciais (título, descrição, responsável, status, estimativa).

