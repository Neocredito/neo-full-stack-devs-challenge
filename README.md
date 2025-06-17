Seja bem-vindo(a) ao nosso desafio técnico. A proposta é avaliar suas habilidades com TypeScript, React, boas práticas de desenvolvimento, legibilidade de código, clareza de organização e capacidade de resolver problemas do mundo real.

## 🎯 Objetivo

Desenvolver uma aplicação full-stack que permita o **cadastro, listagem, filtro, exportação e comunicação em tempo real de propostas**, com uso de mensageria (RabbitMQ).

---

## 📋 Requisitos Funcionais

### 1. Cadastro de Propostas

A aplicação deve permitir o cadastro de uma nova proposta com os seguintes campos obrigatórios:

- Nome (obrigatório)
- CPF (obrigatório)
- Data de nascimento (obrigatório)
- Status (obrigatório): com as opções **"ANÁLISE"** ou **"CONCLUÍDA"**
- Observações:
  - **Deve ser exibido somente se o status for "ANÁLISE"**
  - **Se o status for "CONCLUÍDA" e o campo for enviado, deve ser exibido um erro de validação (não permitir salvar com observações)**

### 2. Listagem de Propostas

- Criar **duas telas distintas**, uma para cada status:
  - Tela de Propostas em **"ANÁLISE"**
  - Tela de Propostas **"CONCLUÍDAS"**
- Cada tela deve exibir a lista de propostas com aquele respectivo status.

### 3. Filtros

- A listagem deve permitir **filtrar pelos seguintes campos** da proposta:
  - Nome
  - CPF
  - Data de nascimento

- Os filtros devem ser aplicados dinamicamente e facilitar a visualização.

### 4. Exportação de Dados

- A aplicação deve permitir **exportar os dados filtrados da listagem atual em formato CSV**.

---

## 🛠️ Requisitos Técnicos

- [ ] Frontend em **React** com **TypeScript**
- [ ] Utilizar **Next.js** como framework frontend
- [ ] Utilizar **Material UI** ou **Tailwind CSS**
- [ ] Backend em **Node.js** com **TypeScript**, utilizando:
  **NestJS** ou **Express**
- [ ] Utilizar **MariaDB** como banco de dados relacional
- [ ] Utilizar **RabbitMQ** como sistema de mensageria

---

## ✅ Critérios de Avaliação

- Aplicação funcional e sem erros
- Implementação correta dos requisitos funcionais
- Clareza e organização do código
- Validações corretas no formulário
- Utilização correta de TypeScript no frontend e backend
- Filtros dinâmicos funcionais
- Exportação em CSV conforme filtros aplicados
- Qualidade da arquitetura proposta
- Uso correto de banco de dados e ORM (opcional: Sequelize, Prisma, TypeORM, etc.)
- A aplicação toda deve rodar em um **docker compose up**

---

## ⚠️ Ambiguidades e Suposições

-  **Tome decisões técnicas razoáveis** com base em boas práticas.
- Documente todas as suposições feitas neste `README.md` ou em um arquivo separado dentro do repositório.

---

## 📦 Entrega

- Faça um fork deste repositório para sua conta no GitHub.
- Crie uma nova branch usando seu nome e sobrenome. Por exemplo: victor-papa.
- Após concluir o desafio, crie um pull request para este repositório (https://github.com/Neocredito/neo-full-stack-devs-challenge), direcionado à branch principal.
- Receberemos uma notificação sobre seu pull request, revisaremos sua solução e entraremos em contato com você.

---

## ❓ Dúvidas

- Em caso de dúvidas, envie mensagem via LinkedIn, para um dos seguintes perfis:
  - [Heverton Costa](https://www.linkedin.com/in/heverton-costa/)
  - [Handryos Ghidorsi dos Santos](https://www.linkedin.com/in/handryos-ghidorsi-dos-santos-421b00258/)
  - [Danilo Gomes Ferraz](https://www.linkedin.com/in/udaanilo/)


**Boa sorte!** Estamos ansiosos para ver sua solução. 🚀
