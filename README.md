# 💼 Desafio Full-Stack Developer - Neo Crédito

Seja bem-vindo(a) ao nosso desafio técnico. A proposta é avaliar suas habilidades com TypeScript, React, boas práticas de desenvolvimento, legibilidade de código, clareza de organização e capacidade de resolver problemas do mundo real.

---

## 🎯 Objetivo

Desenvolver uma aplicação full-stack que permita o **cadastro, listagem, filtro e comunicação em tempo real de propostas**, com uso de mensageria (**RabbitMQ**).

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
> - O comprovante é **enviado para a fila do RabbitMQ**
> - **Caso não ocorra nenhum erro**, o status da proposta é automaticamente alterado para **"CONCLUÍDA"**
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

### 4. Edição de Propostas

- A aplicação deve permitir editar os dados de uma proposta cadastrada através de uma **tela de edição**
- A tela de edição deve conter os seguintes campos:
  - Nome
  - CPF
  - Data de nascimento
  - Status
  - Observações (se status for "AGUARDANDO COMPROVANTE")
  - Comprovante (somente se o status for "AGUARDANDO COMPROVANTE")

> ⚠️ Se a proposta estiver com status **"CONCLUÍDA"**, **todos os campos devem estar desabilitados para edição**, funcionando como modo de visualização bloqueado.  
> A rota pode ser `/propostas/:id/editar` ou similar.

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
- RabbitMQ integrado corretamente
- WebSocket funcionando conforme esperado
- Edição de propostas com bloqueio adequado conforme status
- Arquitetura limpa e sustentável
- Tudo funcional via **Docker Compose**

---

## ⚠️ Dicas

-  **Tome decisões técnicas razoáveis** com base em boas práticas.
- Documente todas as suposições feitas neste README.md ou em um arquivo separado dentro do repositório.

---

## 🎁 BÔNUS

Se quiser ir além dos requisitos obrigatórios e se destacar ainda mais, considere implementar os seguintes pontos:

### ✅ Testes Automatizados

- **Testes de Integração e Unidade**
  - Utilize o **Jest** para testar regras de negócio e fluxos críticos no backend (ex: mudança de status após processamento do comprovante).
- **Testes End-to-End**
  - Implemente testes com **Cypress** para validar o comportamento do sistema em toda a jornada do usuário:
    - Cadastro de proposta com e sem comprovante
    - Edição com bloqueio por status
    - WebSocket funcionando
    - Validações no formulário

### 🔐 Autenticação de Usuário

- Implemente uma **camada de autenticação** simples para proteger as rotas da aplicação:
  - Login com e-mail e senha
  - Proteção nas rotas de cadastro, edição e listagem de propostas
  - Pode utilizar JWT ou sessões (à sua escolha)

> Esses itens não são obrigatórios, mas demonstram atenção à qualidade, segurança e escalabilidade da aplicação.

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
