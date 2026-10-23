# LUS - Localizador de Unidades de Saúde

> **About this repository.** LUS was built by a team during the Trilhas Inova hackathon (challenge 5; the team's original repository is `KayroBrasil/desafio5_trilhas2B_frontend`). This copy is kept by Alexandre Santos, who made the fixes listed in its history (favorites button not refreshing, error handling and general fixes). It needs a separate backend API, configured with `NEXT_PUBLIC_API_BASE_URL`.

Um sistema web moderno para localização e navegação até unidades de saúde, desenvolvido com Next.js 15, TypeScript e integração com Google Maps. O LUS permite aos usuários encontrar rapidamente unidades de saúde próximas, visualizar informações detalhadas e gerenciar favoritos.

## ✨ Características Principais

- Interface moderna e responsiva com suporte a modo escuro/claro
- Integração com Google Maps para localização
- Sistema de busca inteligente por proximidade e tipo de unidade
- Cálculo de rotas otimizadas para diferentes meios de transporte
- Sistema de favoritos personalizado para cada usuário
- Detalhes completos das unidades incluindo fotos, avaliações e contatos

## 🚀 Tecnologias

- **Next.js 15** - Framework React com App Router
- **React 19** - Biblioteca para interfaces de usuário
- **TypeScript** - Tipagem estática
- **Tailwind CSS** - Estilização utilitária
- **Shadcn/ui** - Componentes de interface baseados em Radix UI
- **Google Maps API** - Mapas e localização
- **React Hook Form** - Gerenciamento de formulários
- **Zod** - Validação de schemas
- **Lucide React** - Ícones
- **Next Themes** - Gerenciamento de temas (claro/escuro)
- **Sonner** - Sistema de notificações/toasts
- **Recharts** - Gráficos e visualizações
- **Vaul** - Componente drawer para mobile

## 📋 Funcionalidades

- 🗺️ **Mapa interativo** com localização em tempo real
- 🏥 **Busca de unidades de saúde** por proximidade
- 🚗 **Rotas otimizadas** (carro, transporte público, a pé)
- ⭐ **Sistema de favoritos** para unidades preferidas
- 📱 **Design responsivo** para mobile e desktop
- 🌙 **Modo escuro/claro** alternável
- 📍 **Detalhes das unidades** com fotos e informações
- 🔐 **Sistema de autenticação** de usuários

## 🛠️ Pré-requisitos

- **Node.js** 18.0 ou superior
- **pnpm** 8.0 ou superior
- **Chave da Google Maps API** com os seguintes serviços habilitados:
  - Maps Embed API
  - Maps JavaScript API
  - Places API (New)
  - Distance Matrix API

## 🚀 Instalação e Execução

### 1. Clone o repositório

```bash
git clone https://github.com/sans-script/the-lus-project.git
cd the-lus-project
```

### 2. Instale as dependências

```bash
pnpm install
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env.local` na raiz do projeto:

```bash
cp .env.example .env.local
```

Edite o arquivo `.env.local` e adicione suas configurações:

```env
# Chave de API do Google Maps
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=your_google_maps_api_key_here
# URL base da API utilizada pela aplicação
NEXT_PUBLIC_API_BASE_URL=base_url_here
# Editor padrão para o React (opcional)
REACT_EDITOR=atom
```

### 4. Execute o projeto em desenvolvimento

```bash
pnpm dev
```

O aplicativo estará disponível em `http://localhost:3000`

## 🗂️ Estrutura do Projeto

```
the-lus-project/
├── app/                        # App Router (Next.js 15)
│   ├── auth/                   # Páginas de autenticação
│   ├── globals.css             # Estilos globais
│   ├── layout.tsx              # Layout principal
│   └── page.tsx                # Página inicial
├── components/                 # Componentes React
│   ├── ui/                     # Componentes base (Shadcn/ui)
│   ├── auth-form.tsx           # Formulário de autenticação
│   ├── favorites-list.tsx      # Lista de favoritos
│   ├── favorites-modal.tsx     # Modal de favoritos
│   ├── health-unit-details.tsx # Detalhes da unidade
│   ├── health-unit-locator.tsx # Localizador principal
│   ├── theme-provider.tsx # Provedor de tema
│   ├── theme-toggle.tsx        # Alternador de tema
│   └── user-header.tsx         # Cabeçalho do usuário
├── hooks/                      # Custom React Hooks
│   ├── use-favorites.ts        # Hook de favoritos
│   ├── use-mobile.tsx          # Hook de detecção mobile
│   └── use-toast.ts            # Hook de toast/notificações
├── lib/                        # Utilitários e configurações
│   ├── api.ts                  # Configurações de API
│   ├── auth.ts                 # Autenticação
│   ├── health-units.ts         # Dados das unidades de saúde
│   └── utils.ts                # Funções utilitárias
├── public/                     # Arquivos estáticos
│   ├── placeholder-logo.png
│   ├── placeholder-logo.svg
│   ├── placeholder-user.jpg
│   └── placeholder.svg
├── styles/                     # Estilos adicionais
│   └── globals.css             # Estilos globais adicionais
├── .env.example                # Exemplo de variáveis de ambiente
├── .env.local                  # Variáveis de ambiente (não versionado)
├── next.config.mjs             # Configuração do Next.js
├── tailwind.config.ts          # Configuração do Tailwind CSS
├── tsconfig.json               # Configuração do TypeScript
├── components.json             # Configuração do Shadcn/ui
└── package.json                # Dependências e scripts
```

## 🔑 Configuração da Google Maps API

1. Acesse o [Google Cloud Console](https://console.cloud.google.com/)
2. Crie um novo projeto ou selecione um existente
3. Ative as seguintes APIs:
   - Maps Embed API
   - Maps JavaScript API
   - Places API (New)
   - Distance Matrix API
4. Crie uma chave de API
5. Configure as restrições de domínio (recomendado)
6. Adicione a chave no arquivo `.env.local`:
   ```env
   NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=sua_chave_aqui
   ```
