# 🗂️ PortfolioHUB

> Plataforma centralizada para exibir e gerenciar projetos e portfólios digitais, integrada com GitHub e apoiada pelo Google Gemini.

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![GitHub](https://img.shields.io/badge/versionamento-GitHub-black)
![IA](https://img.shields.io/badge/IA-Google%20Gemini-blue)

---

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Planejamento da Implantação](#1-planejamento-da-implantação)
- [Configuração Inicial e Integração com GitHub](#2-configuração-inicial-e-integração-com-github)
- [Gestão de Usuários e Segurança](#3-gestão-de-usuários-e-segurança)
- [Compartilhamento e Controle de Acesso](#4-compartilhamento-e-controle-de-acesso)
- [Finalização e Testes](#5-finalização-da-integração-e-testes)
- [Revisão Final e Apresentação](#6-revisão-final-e-apresentação)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar](#como-executar)

---

## Sobre o Projeto

O **PortfolioHUB** é uma plataforma digital centralizada desenvolvida para estudantes e profissionais de tecnologia que desejam organizar, versionar e compartilhar seus projetos de forma profissional. A plataforma integra o **GitHub** como sistema de armazenamento e versionamento de código, e utiliza o **Google Gemini** como assistente de inteligência artificial para apoiar as decisões de implantação, segurança e boas práticas de desenvolvimento.

### Objetivos
- Centralizar portfólios digitais em um único ambiente
- Integrar repositórios GitHub diretamente à plataforma
- Garantir segurança e controle de acesso aos projetos
- Utilizar IA (Google Gemini) como guia de implantação

---

## 1. Planejamento da Implantação

### 1.1 Plano de Implantação Detalhado

O processo de implantação foi dividido em **6 fases** com cronograma definido:

| Fase | Descrição | Prazo |
|------|-----------|-------|
| 1 | Planejamento e configuração do Gemini | Dia 1 |
| 2 | Configuração do GitHub e repositório | Dia 2 |
| 3 | Gestão de usuários e políticas de segurança | Dia 3 |
| 4 | Controle de acesso e documentação | Dia 4 |
| 5 | Testes de integração e ajustes finais | Dia 5 |
| 6 | Revisão final e apresentação | Dia 6 |

### 1.2 Uso do Google Gemini como Guia

O **Google Gemini** foi configurado como assistente de IA para apoiar toda a trilha de implantação. As principais interações com o Gemini incluíram:

- **Geração do plano de implantação:** O Gemini foi consultado com o prompt: *"Atue como especialista em DevOps. Crie um plano de implantação completo para uma plataforma de portfólios digitais integrada ao GitHub, incluindo segurança, controle de versão e boas práticas."*
- **Revisão de políticas de segurança:** O Gemini sugeriu a utilização de autenticação em dois fatores (2FA), proteção de branches e políticas de acesso mínimo.
- **Apoio na documentação:** O Gemini auxiliou na estruturação dos arquivos `README.md`, `SECURITY.md` e `CONTRIBUTING.md`.
- **Checklist de lançamento:** O Gemini gerou um checklist de pré-produção com 12 itens de validação.

> 💡 **Prompt usado no Gemini para iniciar a trilha:**
> *"Você é meu guia de implantação. Vou desenvolver o PortfolioHUB, uma plataforma de portfólios digitais integrada ao GitHub. Me ajude a planejar cada etapa, desde a configuração inicial até o lançamento em produção, com foco em segurança e boas práticas."*

---

## 2. Configuração Inicial e Integração com GitHub

### 2.1 Criação do Repositório

O repositório foi criado na conta **[@henrique-ads](https://github.com/henrique-ads)** com as seguintes configurações:

```bash
# Repositório criado via GitHub
Nome: portfoliohub
Visibilidade: Público
Branch padrão: main
Licença: MIT
```

### 2.2 Estrutura de Pastas do Projeto

```
portfoliohub/
├── README.md               # Documentação principal
├── SECURITY.md             # Políticas de segurança
├── CONTRIBUTING.md         # Guia de contribuição
├── LICENSE                 # Licença MIT
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
└── docs/
    ├── implantacao.md      # Documentação detalhada da implantação
    ├── seguranca.md        # Políticas de segurança detalhadas
    └── colaboracao.md      # Práticas de colaboração
```

### 2.3 Configuração do Git Local

```bash
# Configurações iniciais do Git
git config --global user.name "Henrique"
git config --global user.email "seu-email@gmail.com"

# Clonar o repositório
git clone https://github.com/henrique-ads/portfoliohub.git
cd portfoliohub

# Primeiro commit
git add .
git commit -m "feat: estrutura inicial do PortfolioHUB"
git push origin main
```

### 2.4 Integração do GitHub como Armazenamento de Projetos

Cada projeto do portfólio é armazenado como um **repositório individual** no GitHub e referenciado no PortfolioHUB. A integração ocorre via **GitHub API**, permitindo:

- Listagem automática de repositórios públicos do usuário
- Exibição de linguagens de programação utilizadas
- Contagem de stars e forks
- Link direto para o repositório

---

## 3. Gestão de Usuários e Segurança

### 3.1 Configuração de Gestão de Usuários no GitHub

A gestão de usuários foi configurada seguindo o modelo de **menor privilégio**, onde cada colaborador recebe apenas as permissões necessárias para sua função:

| Papel | Permissão no GitHub | Acesso |
|-------|-------------------|--------|
| Owner (Dono) | Admin | Total |
| Colaborador Senior | Write | Push, Pull, Review |
| Colaborador Junior | Read | Pull, Issues |
| Visitante | Read | Apenas visualização |

#### Configuração de Branch Protection

```
Branch: main
✅ Require pull request reviews before merging (mínimo 1 aprovação)
✅ Require status checks to pass before merging
✅ Restrict who can push to matching branches
✅ Do not allow bypassing the above settings
```

### 3.2 Políticas de Segurança com Apoio do Google Gemini

O Google Gemini foi consultado para validar as políticas de segurança implementadas. As principais recomendações seguidas foram:

**Autenticação e Acesso:**
- ✅ Autenticação em dois fatores (2FA) habilitada para todos os colaboradores
- ✅ Uso de SSH keys ao invés de senha para operações Git
- ✅ Personal Access Tokens com escopo mínimo necessário
- ✅ Tokens com data de expiração configurada

**Proteção do Código:**
- ✅ Branch `main` protegida contra push direto
- ✅ Revisão obrigatória de Pull Requests
- ✅ Histórico de commits assinados com GPG
- ✅ Dependabot habilitado para alertas de vulnerabilidades

**Dados Sensíveis:**
- ✅ Arquivo `.gitignore` configurado para excluir arquivos `.env`
- ✅ Nenhuma chave de API ou senha commitada no repositório
- ✅ GitHub Secrets utilizado para variáveis de ambiente sensíveis

> 💡 **Prompt usado no Gemini:**
> *"Quais são as melhores práticas de segurança para um repositório GitHub público que contém uma plataforma de portfólios? Liste políticas de controle de acesso, proteção de dados e prevenção de vazamentos de credenciais."*

---

## 4. Compartilhamento e Controle de Acesso com GitHub

### 4.1 Integração do Repositório

O repositório do PortfolioHUB funciona como **hub central** de versionamento, permitindo:

- **Controle de versão semântico:** seguindo o padrão `v1.0.0`, `v1.1.0`, `v2.0.0`
- **Branches por funcionalidade:** cada nova feature é desenvolvida em branch separada
- **Tags de release:** cada versão estável é marcada com uma tag

#### Fluxo de Trabalho (Git Flow simplificado)

```
main (produção)
  └── develop (desenvolvimento)
        ├── feature/autenticacao-github
        ├── feature/listagem-repositorios
        └── feature/pagina-portfolio
```

### 4.2 Compartilhamento de Código

O repositório é **público**, permitindo que qualquer pessoa:
- Visualize o código-fonte
- Faça fork do projeto
- Abra Issues com sugestões ou bugs
- Contribua via Pull Request seguindo o `CONTRIBUTING.md`

### 4.3 Documentação do Processo de Configuração

Toda a configuração foi documentada nos seguintes arquivos:

- [`CONTRIBUTING.md`](./CONTRIBUTING.md) — guia completo para novos colaboradores
- [`SECURITY.md`](./SECURITY.md) — políticas de segurança e reporte de vulnerabilidades
- [`docs/implantacao.md`](./docs/implantacao.md) — passo a passo detalhado da implantação
- [`docs/colaboracao.md`](./docs/colaboracao.md) — práticas de colaboração e convenções

---

## 5. Finalização da Integração e Testes

### 5.1 Checklist de Integração

Itens verificados com apoio do Google Gemini antes do lançamento:

- [x] Repositório criado e configurado no GitHub
- [x] Branch `main` protegida com regras de revisão
- [x] Autenticação 2FA ativada
- [x] Arquivo `.gitignore` configurado corretamente
- [x] `README.md` completo e informativo
- [x] `SECURITY.md` com política de reporte de vulnerabilidades
- [x] `CONTRIBUTING.md` com guia para colaboradores
- [x] Issues templates configurados
- [x] Pull Request template configurado
- [x] Dependabot habilitado
- [x] Licença MIT adicionada
- [x] Estrutura de pastas organizada

### 5.2 Preparação para Produção

O PortfolioHUB foi preparado para lançamento em produção com as seguintes etapas finais:

```bash
# Tag da versão de lançamento
git tag -a v1.0.0 -m "Release inicial do PortfolioHUB"
git push origin v1.0.0

# Criação da Release no GitHub
# Feito via GitHub UI: Releases > Create new release
# Tag: v1.0.0
# Título: PortfolioHUB v1.0.0 - Lançamento Inicial
```

---

## 6. Revisão Final e Apresentação

### 6.1 Apresentação em Vídeo

A apresentação final do projeto foi gravada e publicada no YouTube, cobrindo:

1. **Introdução** — O que é o PortfolioHUB e qual problema resolve
2. **Demonstração do repositório** — Estrutura, branches e configurações
3. **Segurança implementada** — 2FA, proteção de branch, políticas de acesso
4. **Integração com GitHub** — Como os projetos são armazenados e gerenciados
5. **Uso do Google Gemini** — Como a IA apoiou o processo de implantação
6. **Desafios e soluções** — Principais obstáculos encontrados e como foram resolvidos

> 📺 Link do vídeo: *(a ser publicado)*

### 6.2 Desafios Superados

| Desafio | Solução Implementada |
|---------|---------------------|
| Configuração da proteção de branch | Seguiu guia gerado pelo Google Gemini |
| Definição de permissões por perfil | Tabela de papéis baseada no princípio do menor privilégio |
| Prevenção de vazamento de credenciais | `.gitignore` + GitHub Secrets + auditoria com Gemini |
| Padronização de commits | Conventional Commits + template de PR |

---

## Tecnologias Utilizadas

| Tecnologia | Função |
|-----------|--------|
| GitHub | Versionamento, armazenamento e colaboração |
| Google Gemini | Assistente de IA para guiar a implantação |
| Git | Controle de versão local |
| Markdown | Documentação |
| GitHub Actions | CI/CD (futuro) |

---

## Como Executar

```bash
# 1. Clone o repositório
git clone https://github.com/henrique-ads/portfoliohub.git

# 2. Entre na pasta
cd portfoliohub

# 3. Explore a documentação
cat README.md
```

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.

---



