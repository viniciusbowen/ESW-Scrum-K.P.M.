# Sistema de Gestão Ágil

## Artefato 9 - Descrição da Infraestrutura de Implantação

---

## 1. Introdução

Este documento descreve os requisitos de hardware, software e serviços necessários para a implantação e operação do **Sistema de Gestão Ágil (UnBScrum)** em um ambiente de produção.

A arquitetura de implantação é baseada em um modelo de servidor único (local ou _on-premises_), conforme definido nas restrições do projeto.

---

## 2. Requisitos de Hardware

Para operar o sistema, é necessário um servidor (físico ou máquina virtual) com as seguintes especificações mínimas recomendadas:

- **CPU:** 2 vCPUs (ou processador físico equivalente)
- **Memória (RAM):** 4 GB
- **Armazenamento:** 50 GB de espaço em disco (preferencialmente SSD para melhor performance do banco de dados).
- **Rede:** Interface de rede padrão (ex: Ethernet 1 Gbps) para acesso dos usuários.

---

## 3. Requisitos de Software

O servidor de implantação deve ter os seguintes componentes de software instalados e configurados:

- **Sistema Operacional:** Um sistema operacional de servidor baseado em Linux (Recomendado: **Ubuntu Server 22.04 LTS** ou RHEL/CentOS).
- **Banco de Dados:** **MySQL Server** (Versão 8.0 ou superior).
- **Runtime (Backend):** **Python** (Versão 3.10 ou superior).
- **Servidor de Aplicação WSGI/ASGI:** **Gunicorn** (ou Uvicorn com Gunicorn) para executar a aplicação FastAPI em modo de produção.
- **Servidor Web / Proxy Reverso:** **Nginx** (ou Apache) para servir os arquivos estáticos (HTML/CSS) e atuar como proxy reverso para a aplicação FastAPI.
- **Dependências Python (Bibliotecas):** As bibliotecas listadas no arquivo `requirements.txt` do projeto, incluindo:
  - `fastapi`
  - `sqlalchemy`
  - `mysqlclient` (o driver Python para MySQL)
  - `gunicorn`
  - `uvicorn`

---

## 4. Serviços de Infraestrutura

Para que o sistema funcione, os seguintes serviços devem estar em execução e configurados no servidor:

- **Serviço de Banco de Dados (`mysql.service`):**
  - O serviço do MySQL deve estar em execução e configurado para iniciar automaticamente com o sistema.
  - O banco de dados, usuário e senha da aplicação (conforme `07_projeto_fisico_bd.md`) devem ser criados e as permissões concedidas.
- **Serviço de Aplicação (`gunicorn.service`):**
  - A aplicação FastAPI (Python) deve ser configurada como um serviço de sistema (ex: via `systemd`).
  - Este serviço é gerenciado pelo Gunicorn e é responsável por executar a lógica de negócios e a API RESTful.
- **Serviço de Proxy Reverso (`nginx.service`):**
  - O Nginx deve estar em execução.
  - **Responsabilidade 1:** Servir os arquivos estáticos do frontend (HTML/CSS) diretamente.
  - **Responsabilidade 2:** Atuar como proxy reverso, redirecionando todas as requisições de API (ex: `/api/*`) para o serviço Gunicorn (FastAPI).
- **Serviço de Rede (Firewall):**
  - O firewall do servidor (ex: `ufw`) deve ser configurado para permitir tráfego de entrada nas portas 80 (HTTP) e/ou 443 (HTTPS).
