<h1 align="center">
  <img src="./Logo e fotos/logo.jpeg" width="120px" alt="Sitegen tech Logo" />
  <br>
  Sitegen tech - Sistema Integrado de Gestão
</h1>

<p align="center">
  <img alt="Versão" src="https://img.shields.io/badge/vers%C3%A3o-2.0.0-blue.svg">
  <img alt="Licença" src="https://img.shields.io/badge/license-MIT-green.svg">
  <img alt="Framework" src="https://img.shields.io/badge/Next.js-14-black.svg?logo=next.js">
  <img alt="Estilização" src="https://img.shields.io/badge/TailwindCSS-3-38B2AC.svg?logo=tailwind-css">
</p>

<p align="center">
  <strong>Plataforma completa para gestão de base de conhecimento, pendências, controle de acessos e monitoramento administrativo.</strong>
</p>

---

## ✨ Features

- **Dashboard Executivo:** Visão geral em tempo real com métricas centralizadas e indicadores de saúde operacional.
- **Base de Conhecimento:** Central de artigos, FAQs e documentações com busca inteligente e categorização avançada.
- **Gestão de Pendências:** Tracking de tarefas com status (Andamento, Concluída) e análise de resoluções diárias para garantir que nenhum item se perca.
- **Controle de Acessos:** Gerenciamento seguro de usuários, permissões e endpoints de administração.
- **Gestão de Postos:** Plataforma de gerenciamento de localidades e filiais.
- **Ecossistema Integrado:** Autenticação moderna, design responsivo com Tailwind CSS e componentes acessíveis Shadcn/UI.

## 🚀 Demonstração

### Dashboard Principal
![Dashboard Principal](./Logo%20e%20fotos/Base.png)

### Gestão de Acessos
![Acessos](./Logo%20e%20fotos/Acessos.png)

### Central de Pendências
![Pendências](./Logo%20e%20fotos/Pendencias.png)

---

## 🛠️ Stack Tecnológica

| Camada | Tecnologia Principal | Descrição |
|--------|----------------------|-----------|
| **Frontend** | React + Next.js (App Router) | Renderização híbrida, rotas no sistema de arquivos e server components. |
| **Estilização**| Tailwind CSS + Radix UI | Interface fluida, moderna, dark/light mode e componentes acessíveis (`shadcn/ui`). |
| **Estado** | Zustand / Context API | Gerenciamento de estado global local persistente/temporário. |
| **Backend/DB** | Supabase | Banco de dados PostgreSQL com RLS, Autenticação e APIs serverless embarcadas. |

## ⚡ Instalação Rápida

1. Clone este repositório:
```bash
git clone https://github.com/SeuUsuario/sitegen-tech-gestao.git
cd sitegen-tech-gestao
```

2. Instale as dependências:
```bash
npm install
# ou
pnpm install
```

3. Configure o ambiente:
Crie um arquivo `.env.local` na raiz do projeto com suas chaves de API:
```env
NEXT_PUBLIC_SUPABASE_URL=seu_url_do_supabase
NEXT_PUBLIC_SUPABASE_ANON_KEY=sua_chave_anon_do_supabase
```

4. Execute o servidor de desenvolvimento:
```bash
npm run dev
```
O sistema estará disponível em `http://localhost:3000`.

## 📁 Estrutura do Projeto

```
/
├── app/               # Rotas da aplicação (Next.js App Router)
├── components/        # Componentes UI reutilizáveis (Tailwind, Lucide, Radix)
├── lib/               # Lógicas de configuração, stores (Zustand) e cliente BD
├── public/            # Assets estáticos, logos, etc.
└── scripts/           # Scripts utilitários de banco e dados mock
```

## 🔐 Notas de Segurança (Auditoria de Projeto)

Este repositório foi higienizado e auditado para proteger sua integridade. 
As seguintes ações preventivas foram aplicadas na documentação do código (consulte o relatório do analisador de projetos para mais detalhes):
- **Variáveis Fixadas Removidas:** Tokens e URLs sensíveis do Supabase (`SUPABASE_URL`, etc) foram delegados estritamente ao `.env` que está devidamente mapeado no `.gitignore`.
- **Prevenção de Exposição de Regras de Negócio:** Algoritmos sensíveis originais da empresa (como cálculos proprietários de sessões) não são publicados no frontend portfólio.
- **APIs Limpas:** Nenhum dado massivo de cliente físico está acoplado ao build do front-end. Toda a busca de estatísticas usa clients Supabase com o devido `Auth Middleware`.

## 🤝 Como contribuir

Pull requests são sempre bem-vindos! Se você encontrar oportunidades para melhorar componentes, arrumar um bug ou otimizar integrações, sinta-se à vontade para contribuir. Para mudanças significativas, abra uma _issue_ primeiro para discutirmos o que você gostaria de mudar.

## 📝 Licença

Este projeto está licenciado sob os termos da licença [MIT](./LICENSE).
