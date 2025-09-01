# AIBuddy

An open-source AI chat application that provides a clean and intuitive interface for interacting with various AI models.

## Demo Screenshots

<div align="center">
  <img src="AB1.png" alt="AIBuddy Chat Interface" width="800"/>
  <p><em>Main chat interface with clean and modern design</em></p>
</div>

<div align="center">
  <img src="AB2.png" alt="AIBuddy Model Selection" width="800"/>
  <p><em>Multiple AI provider support and model selection</em></p>
</div>

<div align="center">
  <img src="AB3.png" alt="AIBuddy Settings" width="800"/>
  <p><em>Customizable settings and configuration panel</em></p>
</div>

<div align="center">
  <img src="AB4.png" alt="AIBuddy Conversation History" width="800"/>
  <p><em>Conversation management and history tracking</em></p>
</div>

<div align="center">
  <img src="AB5.png" alt="AIBuddy Dark Theme" width="800"/>
  <p><em>Responsive design with dark theme support</em></p>
</div>

## What is this project?

AIBuddy is a modern web application built with Next.js that allows users to chat with AI models through a user-friendly interface. The application supports multiple AI providers and offers features like conversation management, customizable settings, and local model integration.

## Features

- 🎨 **Clean and responsive chat interface** - Modern UI with dark/light theme support
- 🤖 **Support for multiple AI providers** - OpenAI, Azure OpenAI, Ollama, and more
- 💬 **Conversation history and management** - Save and organize your chat sessions
- 🏠 **Local model support via Ollama** - Run AI models locally for privacy
- 🔒 **Secure data storage with Supabase** - Your conversations are safely stored
- ⚙️ **Customizable user settings** - Personalize your AI chat experience
- 📱 **Mobile-friendly design** - Works seamlessly on all devices
- 🌐 **Multi-language support** - Available in multiple languages

## Quick Demo (No Database Setup Required)

Want to see AIBuddy in action without setting up a database? Follow these steps:

### 1. Clone and Install
```bash
git clone https://github.com/shivas1432/AIBuddy.git
cd AIBuddy
npm install
```

### 2. Create Demo Environment File
```bash
cp .env.local.example .env.local
```

### 3. Add Demo Configuration to `.env.local`
```bash
# Demo Supabase Configuration (for UI preview only)
NEXT_PUBLIC_SUPABASE_URL=http://localhost:54321
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZS1kZW1vIiwicm9sZSI6ImFub24iLCJleHAiOjE5ODM4MTI5OTZ9.CRXP1A7WOeoJeXxjNni43kdQwgnWNReilDMblYTn_I0
SUPABASE_SERVICE_ROLE_KEY=demo-key

# Optional: Add your API key to test actual chat functionality
OPENAI_API_KEY=your_openai_key_here
# OR
ANTHROPIC_API_KEY=your_anthropic_key_here
```

### 4. Run Demo
```bash
npm run dev
```

Visit `http://localhost:3000` to see the AIBuddy interface! 🎉

## Full Installation (Production Setup)

Follow these steps to get AIBuddy running with full functionality on your machine.

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

## Adding AI Provider API Keys

To use external AI providers, add their API keys to your `.env.local` file:

```bash
# OpenAI
OPENAI_API_KEY=your_openai_key_here

# Anthropic Claude
ANTHROPIC_API_KEY=your_anthropic_key_here

# Google Gemini
GOOGLE_GEMINI_API_KEY=your_gemini_key_here

# Azure OpenAI
AZURE_OPENAI_API_KEY=your_azure_key_here
AZURE_OPENAI_ENDPOINT=your_azure_endpoint_here

# Other providers
MISTRAL_API_KEY=your_mistral_key_here
GROQ_API_KEY=your_groq_key_here
PERPLEXITY_API_KEY=your_perplexity_key_here
OPENROUTER_API_KEY=your_openrouter_key_here
```

## Tech Stack

- **Frontend**: Next.js 14, React, TypeScript
- **Styling**: Tailwind CSS, shadcn/ui
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth
- **AI Integration**: Multiple providers support
- **Local AI**: Ollama integration

## Contributing

We welcome contributions! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For questions, issues, or feature requests, please open an issue on GitHub.

## Repository

[https://github.com/shivas1432/AIBuddy](https://github.com/shivas1432/AIBuddy)

---

<div align="center">
  <p>⭐ If you found AIBuddy helpful, please give it a star on GitHub! ⭐</p>
</div>
