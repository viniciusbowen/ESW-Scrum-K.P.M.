# Sistema de Gestão Ágil

## Artefato 7 – Projeto Físico de Banco de Dados

---

### 1\. Introdução

Este documento descreve o **projeto físico do banco de dados** do sistema **Sistema de Gestão Ágil**, responsável por armazenar e organizar as informações utilizadas no gerenciamento de projetos Scrum.  
O modelo foi desenvolvido com base nas entidades principais do domínio (Usuário, Projeto, Sprint, História de Usuário, Tarefa e Papéis) e nos relacionamentos entre elas.

O diagrama físico será implementado no **MySQL**, utilizando **chaves primárias (PK)** e **chaves estrangeiras (FK)** para garantir integridade referencial.

---

### 2\. Tabelas e Relacionamentos

Abaixo são descritas todas as tabelas, seus campos, chaves e relacionamentos.

---

### **2.1. Tabela: USUARIO**

**Descrição:**  
Armazena os dados dos usuários do sistema, incluindo credenciais de acesso e informações pessoais básicas. Cada usuário pode participar de um ou mais projetos e assumir diferentes papéis (Product Owner, Scrum Master, Desenvolvedor).

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_usuario | INT AUTO\_INCREMENT | NÃO | PK | Identificador único do usuário | | nome | VARCHAR(100) | NÃO | | Nome completo do usuário | | email | VARCHAR(100) | NÃO | UNIQUE | E-mail utilizado para login | | senha\_hash | VARCHAR(255) | NÃO | | Senha criptografada | | data\_cadastro | DATETIME | NÃO | | Data de criação do registro | | ativo | BOOLEAN | NÃO | | Indica se o usuário está ativo no sistema |

**Relacionamentos:**

- 1:N com **TAREFA** (usuário pode ser responsável por várias tarefas)  
- N:M com **PROJETO** via tabela **USUARIO\_PROJETO**

---

### **2.2. Tabela: PAPEL**

**Descrição:**  
Define os papéis possíveis dentro de um projeto Scrum (ex: Product Owner, Scrum Master, Desenvolvedor).

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_papel | INT AUTO\_INCREMENT | NÃO | PK | Identificador único do papel | | nome\_papel | VARCHAR(50) | NÃO | | Nome do papel (Product Owner, etc.) | | descricao | VARCHAR(255) | SIM | | Breve descrição da função no projeto |

**Relacionamentos:**

- N:M com **USUARIO\_PROJETO** (define o papel de um usuário em cada projeto)

---

### **2.3. Tabela: PROJETO**

**Descrição:**  
Representa um projeto Scrum dentro do sistema, contendo informações gerais e associando usuários e sprints.

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_projeto | INT AUTO\_INCREMENT | NÃO | PK | Identificador único do projeto | | nome | VARCHAR(100) | NÃO | | Nome do projeto | | descricao | TEXT | SIM | | Descrição detalhada do projeto | | data\_inicio | DATE | NÃO | | Data de início planejada | | data\_fim | DATE | SIM | | Data de término planejada | | status | ENUM('Planejado','Em andamento','Concluído','Cancelado') | NÃO | | Estado atual do projeto |

**Relacionamentos:**

- 1:N com **SPRINT**  
- N:M com **USUARIO** via **USUARIO\_PROJETO**

---

### **2.4. Tabela: USUARIO\_PROJETO**

**Descrição:**  
Tabela de associação que vincula usuários a projetos e define seus papéis dentro de cada um.

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_usuario | INT | NÃO | PK, FK | Identificador do usuário | | id\_projeto | INT | NÃO | PK, FK | Identificador do projeto | | id\_papel | INT | NÃO | FK | Papel exercido no projeto | | data\_vinculo | DATETIME | NÃO | | Data de associação ao projeto |

**Relacionamentos:**

- FK (id\_usuario) → **USUARIO(id\_usuario)**  
- FK (id\_projeto) → **PROJETO(id\_projeto)**  
- FK (id\_papel) → **PAPEL(id\_papel)**

---

### **2.5. Tabela: SPRINT**

**Descrição:**  
Contém os dados das sprints de cada projeto, como objetivo, duração e status.

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_sprint | INT AUTO\_INCREMENT | NÃO | PK | Identificador da sprint | | id\_projeto | INT | NÃO | FK | Projeto ao qual a sprint pertence | | nome | VARCHAR(100) | NÃO | | Nome ou objetivo da sprint | | data\_inicio | DATE | NÃO | | Data de início da sprint | | data\_fim | DATE | NÃO | | Data de término da sprint | | status | ENUM('Planejada','Em andamento','Encerrada') | NÃO | | Situação atual da sprint |

**Relacionamentos:**

- FK (id\_projeto) → **PROJETO(id\_projeto)**  
- 1:N com **HISTORIA\_USUARIO**

---

### **2.6. Tabela: HISTORIA\_USUARIO**

**Descrição:**  
Armazena as histórias de usuário associadas a cada sprint, representando requisitos funcionais descritos em formato ágil.

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_historia | INT AUTO\_INCREMENT | NÃO | PK | Identificador da história | | id\_sprint | INT | NÃO | FK | Sprint associada | | titulo | VARCHAR(100) | NÃO | | Título resumido da história | | descricao | TEXT | SIM | | Descrição detalhada da história | | prioridade | ENUM('Alta','Média','Baixa') | NÃO | | Grau de prioridade | | pontos | INT | SIM | | Pontuação atribuída (story points) | | status | ENUM('To Do','Doing','Done') | NÃO | | Estado atual da história |

**Relacionamentos:**

- FK (id\_sprint) → **SPRINT(id\_sprint)**  
- 1:N com **TAREFA**

---

### **2.7. Tabela: TAREFA**

**Descrição:**  
Representa as tarefas específicas derivadas de uma história de usuário. Cada tarefa pode ser atribuída a um desenvolvedor.

**Campos:**  
| Campo | Tipo | Nulo | Chave | Descrição | |-------|------|------|--------|-----------| | id\_tarefa | INT AUTO\_INCREMENT | NÃO | PK | Identificador da tarefa | | id\_historia | INT | NÃO | FK | História de usuário associada | | id\_usuario\_responsavel | INT | SIM | FK | Usuário responsável pela execução | | titulo | VARCHAR(100) | NÃO | | Nome curto da tarefa | | descricao | TEXT | SIM | | Detalhamento da tarefa | | status | ENUM('To Do','Doing','Done') | NÃO | | Situação atual | | data\_criacao | DATETIME | NÃO | | Data de criação | | data\_conclusao | DATETIME | SIM | | Data de conclusão |

**Relacionamentos:**

- FK (id\_historia) → **HISTORIA\_USUARIO(id\_historia)**  
- FK (id\_usuario\_responsavel) → **USUARIO(id\_usuario)**

---

### 3\. Resumo de Relacionamentos

- **USUARIO** ↔ **PROJETO**: N:M (via USUARIO\_PROJETO)  
- **PROJETO** ↔ **SPRINT**: 1:N  
- **SPRINT** ↔ **HISTORIA\_USUARIO**: 1:N  
- **HISTORIA\_USUARIO** ↔ **TAREFA**: 1:N  
- **USUARIO** ↔ **TAREFA**: 1:N (um usuário pode ter várias tarefas)  
- **PAPEL** ↔ **USUARIO\_PROJETO**: 1:N

---

### 4\. Observações Técnicas

- Todas as tabelas utilizam **engine InnoDB** para suportar transações e integridade referencial.  
- Campos de data seguem padrão **DATETIME** com fuso horário configurável.  
- Índices secundários serão criados em colunas de busca frequente (como `email`, `id_projeto`, `id_sprint`).  
- As colunas ENUM podem ser ajustadas conforme a evolução do projeto e da metodologia Scrum adotada.

---

