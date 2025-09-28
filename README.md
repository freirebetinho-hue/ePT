# Sistema de Permissão de Trabalho (e-PT)

![Demonstração do Dashboard](https://images.unsplash.com/photo-1552879890-3a06dd3a06c2?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=M3w3NDE5ODJ8MHwxfHNlYXJjaHw1fHxjb25zdHJ1Y3Rpb24lMjBzYWZldHl8ZW58MHx8fHwxNzU4ODQyODY5fDA&ixlib=rb-4.1.0&q=80&w=1080)

Um protótipo de Sistema de Permissão de Trabalho (PTW) moderno e digital, construído para otimizar e garantir a segurança em ambientes de trabalho de alto risco. O sistema é desenvolvido com Next.js, Firebase (simulado com localStorage) e Google AI (Genkit).

## ✨ Funcionalidades Principais

- **Criação de Permissões Dinâmicas**: Formulários customizados para diferentes tipos de permissões, incluindo:
  - Trabalho a Quente
  - Espaço Confinado
  - Trabalho em Altura
  - Permissão para Grua (PTG)
- **Fluxo de Aprovação Digital**: Assinaturas eletrônicas e biométricas (captura facial) para aprovação por múltiplos responsáveis.
- **Validação com Inteligência Artificial**: Uso do Genkit para analisar a geolocalização do trabalhador e validar se a área é apropriada para o trabalho.
- **Controle de Acesso por Função**: Sistema de permissões para Administradores, Engenheiros e Técnicos de Segurança.
- **Gerenciamento Centralizado**: Módulos para gerenciar Obras, Usuários e Configurações do sistema.
- **Geração de QR Code**: Crie QR Codes para cada permissão, permitindo acesso rápido aos detalhes e status em campo.
- **Geração de PDF**: Exporte permissões completas para o formato PDF, com cabeçalho padrão ISO e paginação automática.
- **Dashboard Intuitivo**: Visão geral com métricas de permissões ativas, pendentes e fechadas, além de um gráfico de distribuição.
- **Log de Atividades**: Rastreie as principais ações realizadas no sistema para auditoria e conformidade.
- **Personalização**: Altere o logo da empresa e gerencie os detalhes de revisão de cada documento de permissão.

## 🚀 Tecnologias Utilizadas

- **Frontend**: [Next.js](https://nextjs.org/) (com App Router) e [React](https://reactjs.org/)
- **UI/Componentes**: [ShadCN/UI](https://ui.shadcn.com/), [Tailwind CSS](https://tailwindcss.com/) e [Lucide Icons](https://lucide.dev/)
- **Inteligência Artificial**: [Genkit](https://firebase.google.com/docs/genkit) para integração com modelos Google AI (Gemini).
- **Gráficos**: [Recharts](https://recharts.org/)
- **Formulários**: [React Hook Form](https://react-hook-form.com/) com validação via [Zod](https://zod.dev/)
- **Geração de PDF**: [jsPDF](https://github.com/parallax/jsPDF) e [html2canvas](https://html2canvas.hertzen.com/)
- **Persistência de Dados**: `localStorage` (simulando um banco de dados para o protótipo).

## ⚙️ Como Iniciar

Siga os passos abaixo para configurar e executar o projeto localmente.

### 1. Pré-requisitos

- [Node.js](https://nodejs.org/) (versão 20.x ou superior)
- [npm](https://www.npmjs.com/) (geralmente vem com o Node.js)

### 2. Instalação

Clone o repositório e instale as dependências:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
npm install
```

### 3. Configuração do Ambiente

Crie um arquivo `.env` na raiz do projeto, copiando o conteúdo do arquivo `.env.example` (se existir). Preencha as variáveis necessárias, especialmente as chaves de API para os serviços do Google.

```env
# Chaves para a API do Google AI (Gemini) e Google Maps
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY="SUA_CHAVE_API_DO_GOOGLE_MAPS"
GEMINI_API_KEY="SUA_CHAVE_API_DO_GEMINI"
```

> **Nota**: Para o protótipo, a autenticação e o banco de dados do Firebase são simulados via `localStorage`, então as credenciais do Firebase não são estritamente necessárias para executar o app localmente, mas são importantes para a integração com Genkit e futuras expansões.

### 4. Executando o Servidor de Desenvolvimento

Execute o seguinte comando para iniciar o aplicativo em modo de desenvolvimento:

```bash
npm run dev
```

Abra [http://localhost:3000](http://localhost:3000) no seu navegador para ver o resultado.

### 5. Executando o Genkit (Opcional)

Se você precisar testar ou depurar os fluxos de IA localmente, inicie o servidor do Genkit em um terminal separado:

```bash
npm run genkit:dev
```

Isso iniciará a UI de desenvolvimento do Genkit em `http://localhost:4000`.

## 🚢 Implantação

O projeto está pré-configurado para implantação no **Firebase App Hosting**.

1.  **Instale o Firebase CLI**: Se ainda não tiver, instale a CLI do Firebase globalmente.
    ```bash
    npm install -g firebase-tools
    ```
2.  **Login e Inicialização**: Faça login e inicialize o Firebase no seu projeto.
    ```bash
    firebase login
    firebase init apphosting
    ```
3.  **Implantação**: Execute o comando de deploy.
    ```bash
    firebase deploy --only hosting
    ```

O arquivo `apphosting.yaml` na raiz do projeto já contém as configurações básicas para a implantação.
