# SINAN - Sistema de Informação de Agravos de Notificação

![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)

## Sobre o Projeto

O SINAN é uma plataforma essencial para a vigilância epidemiológica no Brasil, permitindo o registro, monitoramento e análise sistemática de doenças e agravos de notificação compulsória. 

Este repositório central unifica o desenvolvimento de um **ecossistema completo e moderno**, composto por um backend robusto em Python/Django e uma interface intuitiva em Next.js/TypeScript.

## Arquitetura

### Backend (Python/Django)
API RESTful que atua como servidor principal e fonte única da verdade para os dados.

- Django 6.0.4, PostgreSQL, python-dotenv
- Padrão Snapshot para integridade histórica de notificações
- Modelos: Unidade, Usuário, Paciente, Notificação e variantes por tipo de agravo

### Frontend (Next.js/TypeScript)
Interface moderna, responsiva e performática.

- Next.js, TypeScript, Tailwind CSS, shadcn/ui
- React Hook Form, Zod, TanStack Query, Axios
- Suporte a modo mock para desenvolvimento offline

## Repositórios

| Repositório                                                   | Descrição               | Tecnologias |
|---------------------------------------------------------------|-------------------------|---|
| [backend-sinan](https://github.com/SINAN-UFSM/backend-sinan)  | API e lógica de negócio | Django 6, PostgreSQL, Python |
| [sinan-frontend](https://github.com/SINAN-UFSM/sinan-frontend) | Interface web           | Next.js, TypeScript, Tailwind CSS |
| [sinan-docs](https://github.com/SINAN-UFSM/sinan-docs)   | Documentos  |

## Início Rápido

Consulte os READMEs específicos para instruções detalhadas:

- **Backend:** [backend-sinan](https://github.com/SINAN-UFSM/backend-sinan)
- **Frontend:** [sinan-frontend](https://github.com/SINAN-UFSM/sinan-frontend)

### Pré-requisitos

- Python 3.12+ (backend)
- Node.js 18+ (frontend)
- PostgreSQL 12+

## Rotas Principais

**Backend:**
- `/health/` - Verificação de disponibilidade
- `/admin/` - Painel administrativo Django

**Frontend:**
- `/` - Página inicial
- `/dashboard` - Painel de controle
- `/notifications` - Gerenciamento de notificações
- `/patients` - Gerenciamento de pacientes
- `/units` - Gerenciamento de unidades de saúde
- `/reports` - Relatórios e análises

---

## Fluxo de Desenvolvimento

1. **Backend:** API processa e armazena os dados de notificação com snapshots históricos
2. **Frontend:** Interface captura dados via formulários e os envia para a API REST
3. **Banco de Dados:** PostgreSQL mantém os dados com integridade referencial e histórica
4. **Comunicação:** JSON via HTTP/HTTPS entre frontend e backend

---

## Padrão Snapshot

A arquitetura implementa um padrão de "snapshot" nos modelos de notificação. Isto garante que:

- **Dados Imutáveis:** CPF, data de nascimento, cidade de nascimento e raça/cor são capturados e congelados no momento da notificação
- **Dados Mutáveis:** Nome, sexo, escolaridade e endereço também são capturados como snapshot
- **Integridade Histórica:** Futuras alterações no cadastro mestre do paciente não afetam as notificações existentes
- **Conformidade Legal:** Atende aos requisitos regulatórios de preservação de dados históricos para vigilância epidemiológica

### Tipos de Notificação

O sistema suporta múltiplos tipos de agravos, cada um com campos específicos:

- AIDS
- Botulismo
- Epizootia
- Esquistossomose
- Febre Amarela
- Dengue/Chikungunya
- Animal Peçonhento
- Anti-Rábico
- Cólera
- Chikungunya
- Coqueluche

---

## Observações Importantes
- Em desenvolvimento, o frontend suporta modo mock (`NEXT_PUBLIC_USE_MOCKS=true`) para testar sem o backend
- O PostgreSQL deve estar em execução antes de iniciar o backend
- Em produção, altere `DJANGO_DEBUG=False` para segurança
- A comunicação entre frontend e backend ocorre via API REST com autenticação via Bearer Token

---

## Contribuição

Para contribuir com melhorias ou correções:

1. Faça um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b feature/sua-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/sua-feature`)
5. Abra um Pull Request com descrição detalhada das alterações

---

## Suporte e Documentação

Para mais detalhes sobre cada componente:

- **Backend:** Veja o [README do backend-sinan](https://github.com/SINAN-UFSM/backend-sinan/blob/main/README.md)
- **Frontend:** Veja o [README do sinan-frontend](https://github.com/SINAN-UFSM/sinan-frontend/blob/main/README.md)

---


## Contato e Informações

**Organização:** SINAN-UFSM  
**Objetivo:** Modernização do Sistema de Informação de Agravos de Notificação  
**Foco:** Vigilância epidemiológica de doenças e agravos de notificação compulsória no Brasil
