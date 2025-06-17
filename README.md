# 💼 Desafio Full-Stack Developer - Neo crédito

Seja bem-vindo(a) ao nosso desafio técnico. A proposta é avaliar suas habilidades com TypeScript, React, boas práticas de desenvolvimento, legibilidade de código, clareza de organização e capacidade de resolver problemas do mundo real.

---

## 🎯 Objetivo

Desenvolver uma aplicação full-stack que permita o **cadastro, listagem, filtro, exportação e comunicação em tempo real de propostas**, com uso de mensageria (**RabbitMQ**).

---

## 📋 Requisitos Funcionais

### 1. Cadastro de Propostas

A aplicação deve permitir o cadastro de uma nova proposta com os seguintes campos obrigatórios:

- Nome (obrigatório)
- CPF (obrigatório)
- Data de nascimento (obrigatório)
- Status (obrigatório): com as opções **"AGUARDANDO COMPROVANTE"** ou **"CONCLUÍDA"**
- Importar comprovante (obrigatório): aceita apenas **PDF**  
  > ⚠️ Somente exibido quando o status for **"AGUARDANDO COMPROVANTE"**  
  > O conteúdo do PDF será convertido para **plain-text** e armazenado no banco de dados
- Observações:
  - Deve ser exibido **somente se o status for "AGUARDANDO COMPROVANTE"**
  - Se o status for **"CONCLUÍDA"** e o campo for enviado, deve gerar um **erro de validação**

> **Fluxo especial (RabbitMQ + WebSocket)**  
> Ao importar o comprovante com o status "AGUARDANDO COMPROVANTE" e submeter o formulário:
> - **Caso não ocorra nenhum erro**, o status da proposta é automaticamente alterado para **"CONCLUÍDA"**
> - A proposta é **enviada para a fila RabbitMQ**
> - Um **WebSocket** informa em tempo real o estado do processamento:
>   - `Processando...`
>   - `Concluído!`

---

### 2. Listagem de Propostas

- Duas telas distintas:
  - Propostas em **"AGUARDANDO COMPROVANTE"**
  - Propostas **"CONCLUÍDAS"**
- Ambas exibem os dados em tabela, separadas por status

---

### 3. Filtros

- Os filtros disponíveis devem ser aplicáveis dinamicamente:
  - Nome
  - CPF
  - Data de nascimento

---

### 4. Exportação de Dados

- Exportar as propostas filtradas da listagem atual em **formato CSV**

---

### 5. Exibição Detalhada da Proposta

- A aplicação deve permitir visualizar **todos os dados da proposta cadastrada** em um **componente de visualização detalhada**, incluindo:
  - Nome
  - CPF
  - Data de nascimento
  - Status
  - Observações (somente se houver e o status for "AGUARDANDO COMPROVANTE")
  - Comprovante: mostrar o conteúdo extraído em texto do arquivo PDF

> Essa exibição pode ser feita em um modal, drawer ou nova rota (`/propostas/:id`), conforme decisão técnica.  
> A exibição do **conteúdo do comprovante** deve deixar claro que se trata do **texto extraído do PDF**, não o arquivo binário.

---

## 🛠️ Requisitos Técnicos

- [x] **Frontend**
  - React com TypeScript
  - Framework: **Next.js**
  - Estilização: **Material UI** ou **Tailwind CSS**
- [x] **Backend**
  - Node.js com TypeScript (NestJS ou Express.js)
  - Banco de dados: **MariaDB**
  - Sistema de mensageria: **RabbitMQ**
  - Comunicação em tempo real: **WebSocket**
- [x] A aplicação deve rodar com `docker-compose up`

---

## ✅ Critérios de Avaliação

- Funcionalidade completa e sem erros
- Validações corretas e rigorosas
- Código limpo e organizado
- Uso adequado de TypeScript (frontend e backend)
- Exportação CSV com filtros aplicados
- RabbitMQ integrado corretamente
- WebSocket funcionando conforme esperado
- Visualização detalhada dos dados da proposta
- Arquitetura limpa e sustentável
- Tudo funcional via **Docker Compose**

---

## ⚠️ Ambiguidades e Suposições

- O campo de **comprovante** só aparece quando o status for "AGUARDANDO COMPROVANTE"
- Após o upload e envio da proposta, o **status é automaticamente alterado** para "CONCLUÍDA"
- A fila RabbitMQ pode ser nomeada como `fila.processarProposta`
- O processamento é simulado e exibido em tempo real via WebSocket com status como `processando`, `concluído`
- O conteúdo dos arquivos PDF será extraído com uma lib como `pdf-parse`
- A visualização de detalhes pode ser por rota dedicada, modal ou drawer

---

## 📦 Entrega

- Faça um fork deste repositório: [https://github.com/Neocredito/neo-full-stack-devs-challenge](https://github.com/Neocredito/neo-full-stack-devs-challenge)
- Crie uma branch com seu nome e sobrenome, por exemplo: `handryos-santos`
- Ao finalizar, abra um **Pull Request** para a `main` do repositório original

---

## ❓ Dúvidas

- Em caso de dúvidas, envie mensagem via LinkedIn, para um dos seguintes perfis:
  - [Heverton Costa](https://www.linkedin.com/in/heverton-costa/)
  - [Handryos Ghidorsi dos Santos](https://www.linkedin.com/in/handryos-ghidorsi-dos-santos-421b00258/)
  - [Danilo Gomes Ferraz](https://www.linkedin.com/in/udaanilo/)

---

**Boa sorte!** Estamos ansiosos para ver sua solução. 🚀
