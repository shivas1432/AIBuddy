# AIBuddy

An open-source AI chat application that provides a clean and intuitive interface for interacting with various AI models.

## What is this project?

AIBuddy is a modern web application built with Next.js that allows users to chat with AI models through a user-friendly interface. The application supports multiple AI providers and offers features like conversation management, customizable settings, and local model integration.

## Features

- Clean and responsive chat interface
- Support for multiple AI providers (OpenAI, Azure OpenAI, Ollama)
- Conversation history and management
- Local model support via Ollama
- Secure data storage with Supabase
- Customizable user settings

## Installation

Follow these steps to get heyBuddy running locally on your machine.

### Prerequisites

- Node.js (v18 or higher)
- Docker (for Supabase)
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/shivas1432/AIBuddy.git
cd AIBuddy
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Setup Supabase (Database)

#### Install Supabase CLI

**MacOS/Linux:**
```bash
brew install supabase/tap/supabase
```

**Windows:**
```bash
scoop bucket add supabase https://github.com/supabase/scoop-bucket.git
scoop install supabase
```

#### Start Supabase

```bash
supabase start
```

### 4. Configure Environment Variables

Copy the example environment file:

```bash
cp .env.local.example .env.local
```

Get the required values by running:

```bash
supabase status
```

Open `.env.local` and fill in the values from the `supabase status` output:
- Use the `API URL` for `NEXT_PUBLIC_SUPABASE_URL`
- Use the `anon key` for `NEXT_PUBLIC_SUPABASE_ANON_KEY`
- Use the `service_role key` for `SUPABASE_SERVICE_ROLE_KEY`

### 5. Setup Database

In the file `supabase/migrations/20240108234540_setup.sql`, update these values (around lines 53-54):
- `project_url`: Use `http://supabase_kong_chatbotui:8000` (default)
- `service_role_key`: Use the service role key from `supabase status`

### 6. Install Ollama (Optional - for local AI models)

If you want to use local AI models, install Ollama by following the instructions at [https://ollama.com](https://ollama.com).

### 7. Run the Application

```bash
npm run chat
```

The application will be available at [http://localhost:3000](http://localhost:3000).

You can access the database management interface at [http://localhost:54323/project/default/editor](http://localhost:54323/project/default/editor).

## Adding API Keys

To use external AI providers, add their API keys to your `.env.local` file:

```bash
OPENAI_API_KEY=your_openai_key_here
AZURE_OPENAI_API_KEY=your_azure_key_here
AZURE_OPENAI_ENDPOINT=your_azure_endpoint_here
```

## Support

For questions, issues, or feature requests, please open an issue on GitHub.

## Repository

[https://github.com/shivas1432/AIBuddy](https://github.com/shivas1432/heyBuddy)