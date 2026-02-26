---
name: project-analyzer
description: Analisa a estrutura de um projeto, mapeia funcionalidades, identifica arquivos importantes e suas responsabilidades, e detecta informações sensíveis como APIs expostas, variáveis de ambiente e dados não publicáveis.
---

# Project Analyzer - Análise de Funcionalidades e Segurança de Projetos

O Project Analyzer é uma skill projetada para fornecer uma visão abrangente da estrutura e do conteúdo de um projeto de software. Seu objetivo principal é auxiliar na compreensão rápida de um codebase, destacando os componentes críticos e alertando sobre potenciais vulnerabilidades ou informações sensíveis que não deveriam ser expostas.

## Como Usar

Para utilizar esta skill, basta solicitar ao Antigravity que realize uma "análise de projeto" ou "auditoria de código" em um diretório específico. O Antigravity irá então escanear os arquivos do projeto e gerar um relatório detalhado.

## Áreas de Análise

A skill Project Analyzer foca nas seguintes áreas:

### 1. Mapeamento de Funcionalidades

Identifica as principais funcionalidades e módulos do projeto, descrevendo o propósito de cada um. Isso inclui:

*   **Visão Geral do Projeto**: Um resumo das capacidades e objetivos do software.
*   **Módulos e Componentes**: Listagem dos principais módulos, suas interdependências e as funcionalidades que implementam.
*   **Fluxos de Trabalho**: Descrição dos fluxos de dados e interações entre diferentes partes do sistema.

### 2. Identificação de Arquivos Importantes e Responsabilidades

Lista os arquivos e diretórios mais relevantes do projeto, explicando sua função e importância no contexto geral. Exemplos incluem:

*   `package.json` / `pom.xml` / `requirements.txt`: Gerenciamento de dependências.
*   `README.md`: Documentação principal do projeto.
*   Arquivos de configuração (e.g., `.json`, `.yaml`, `.xml`): Configurações do ambiente e da aplicação.
*   Arquivos de rotas (e.g., `routes/index.js`, `urls.py`): Definição de endpoints da API.
*   Controladores/Handlers (e.g., `controllers/userController.js`, `views.py`): Lógica de negócio e manipulação de requisições.
*   Modelos/Schemas (e.g., `models/User.js`, `schema.prisma`): Estrutura de dados e interação com o banco de dados.
*   Serviços/Utilitários: Funções auxiliares e lógica de serviço.

### 3. Detecção de Arquivos e Dados Sensíveis

Escaneia o projeto em busca de informações que não deveriam ser publicadas ou expostas, incluindo:

*   **Variáveis de Ambiente (`.env`)**: Arquivos que contêm chaves de API, credenciais de banco de dados, segredos e outras configurações sensíveis.
*   **APIs Expostas**: Identificação de endpoints de API que podem estar acessíveis publicamente e que podem conter vulnerabilidades ou expor dados desnecessariamente.
*   **Credenciais Hardcoded**: Busca por chaves de API, senhas, tokens ou outros segredos embutidos diretamente no código-fonte.
*   **Dados Pessoais/Confidenciais**: Alerta sobre a presença de dados que podem ser considerados sensíveis (e.g., PII - Personally Identifiable Information) em locais inadequados.

## Formato do Relatório de Análise

O output da skill será um relatório em formato Markdown, estruturado da seguinte forma:

```markdown
# Relatório de Análise de Projeto: [Nome do Projeto]

## Visão Geral

[Breve descrição do projeto e suas funcionalidades principais.]

## Mapeamento de Funcionalidades

| Funcionalidade | Descrição | Módulos Relacionados | Arquivos Chave |
|----------------|-----------|----------------------|----------------|
| [Nome Func 1]  | [Desc.]   | [Módulo A, Módulo B] | [arq1.js, arq2.py] |
| [Nome Func 2]  | [Desc.]   | [Módulo C]           | [arq3.java]    |

## Arquivos Importantes e Responsabilidades

| Arquivo/Diretório | Responsabilidade Principal | Descrição Detalhada |
|-------------------|----------------------------|---------------------|
| `package.json`    | Gerenciamento de Dependências | Define dependências do projeto, scripts e metadados. |
| `src/controllers/`| Lógica de Negócio          | Contém a lógica para processar requisições e interagir com modelos. |
| `.env`            | Variáveis de Ambiente      | Armazena configurações sensíveis e específicas do ambiente. |

## Detecção de Informações Sensíveis

### Variáveis de Ambiente

*   **Arquivo**: `.env`
    *   **Conteúdo Potencialmente Sensível**: `DB_PASSWORD`, `API_KEY`, `STRIPE_SECRET_KEY`
    *   **Recomendação**: Garantir que este arquivo não seja versionado e que as variáveis sejam acessadas de forma segura.

### APIs Expostas

*   **Endpoint**: `/api/v1/admin/users`
    *   **Métodos**: `GET`, `POST`
    *   **Potencial Vulnerabilidade**: Acesso sem autenticação adequada ou exposição de dados de usuário sensíveis.
    *   **Recomendação**: Implementar autenticação robusta e controle de acesso baseado em funções.

### Credenciais Hardcoded

*   **Arquivo**: `src/utils/auth.js` (Linha 42)
    *   **Conteúdo**: `const SECRET_KEY = "mySuperSecretKey123";`
    *   **Recomendação**: Mover para variáveis de ambiente ou um serviço de gerenciamento de segredos.

### Outros Dados Confidenciais

*   **Arquivo**: `src/data/users.json`
    *   **Conteúdo**: Contém dados de usuários de teste com informações de PII.
    *   **Recomendação**: Remover dados sensíveis de arquivos versionados e usar dados fictícios ou anonimizados para desenvolvimento.
```

## Princípios de Análise

1.  **Abrangência**: Escanear o máximo de arquivos relevantes para uma análise completa.
2.  **Contextualização**: Entender o papel de cada arquivo e sua relação com o todo.
3.  **Segurança em Primeiro Lugar**: Priorizar a identificação de vulnerabilidades e dados sensíveis.
4.  **Clareza no Relatório**: Apresentar as informações de forma organizada e fácil de entender.

Esta skill visa ser uma ferramenta valiosa para desenvolvedores e auditores de segurança, agilizando o processo de entendimento e avaliação de projetos de software.
