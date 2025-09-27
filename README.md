# FADA - Your Family's Financial Assistant 🤝💰

**AI financial guidance that actually works for working families**

FADA (Financial Assistant for Data Analytics) is your personal AI financial coach, built specifically for families who work hard but struggle to get ahead financially. No fancy jargon, no sales pitches, just practical help that fits your real life.

> **For Users**: This guide shows you how to use FADA to improve your finances  
> **For Developers**: See the [Developer Guide](developer_guide.md) for technical setup and implementation details

## 🆕 Multi-Agent Architecture

FADA now uses a powerful multi-agent system to provide specialized support:

- **FADA Planning Agent**: Your personal financial coach for onboarding, goal setting, and creating actionable plans
- **FADA Analytics Agent**: Your data analyst for calculations, forecasting, and document analysis
- **Shared Configuration**: Ensures both agents follow the same security standards and data formats

This architecture allows FADA to work within platform limitations while providing even better specialized support for your financial journey.

## Why FADA Exists

Most financial advice is written for people who already have money. FADA is different - we're built for families who:
- Work paycheck to paycheck but want to build wealth
- Juggle multiple debts while raising kids
- Need simple, clear advice without the financial industry complexity
- Want to teach their kids about money the right way
- Are tired of being told they need to "just budget better"

## What Makes FADA Different

### 🎯 **Built for Real Families**
- Understands the challenges of working parents
- Knows that "just cut your coffee" won't fix real financial problems
- Focuses on building wealth, not just surviving

### 📊 **Your Data, Your Control**
- You control what information to share
- Update it whenever your situation changes
- Seamless handoff between Planning and Analytics agents

### ⚡ **Quick & Practical**
- Get started in 15 minutes, not 15 hours
- Clear next steps you can actually do
- No overwhelming spreadsheets or complex tools

### 🏠 **Family-Focused Planning**
- Balances today's needs with tomorrow's dreams
- Helps you save for your kids' future
- Makes retirement planning simple and achievable

## How It Works

### New to FADA?
1. Start with the **FADA Planning Agent** - it will guide you through a 15-minute conversation about your family, income, expenses, and goals
2. Get your personalized financial plan with immediate action steps
3. When you need detailed analysis, use the **FADA Analytics Agent** with your saved profile

### Already have a profile?
Upload your FADA knowledge base file to either agent and pick up right where you left off. The Planning Agent helps refine your goals, while the Analytics Agent provides deep insights and calculations.

## What You Get

- **Smart Budgeting**: A budget that actually works for your family's real expenses
- **Debt Strategy**: Clear plan to pay off debts faster and save money on interest  
- **Emergency Fund**: Step-by-step guide to build financial security
- **Investment Help**: Simple strategies for retirement and college savings
- **Progress Tracking**: See how you're improving over time
- **Goal Planning**: Turn dreams into achievable financial plans

## Getting Started

Ready to take control of your family's finances? Just start a conversation with FADA Planning Agent and say "I need help with my finances."

## Where to Find FADA

FADA can be hosted on multiple AI platforms:

- **🤖 ChatGPT** - You can create two "FADA Planning" and "FADA Analytics" custom GPTs
- **🧠 Claude** - Create these agents as Claude Projects
- **🌟 Mistral AI** - Create a custom Agent on Le Chat Pro
- **💻 Self-Host** - Run privately on your own computer with Ollama and Open WebUI

## Quick Setup (5 Minutes)

Want to create your own private FADA agents? Here's the simplest way on each platform:

### 📁 What You'll Need
Download these 3 files from this repository:
- `fada_planning_agent.system.prompt.md` - The planning agent's instructions
- `fada_analytics_agent.system.prompt.md` - The analytics agent's instructions  
- `fada_shared_config.json` - Security and data settings (REQUIRED for both agents)

### 🤖 ChatGPT (Easiest)
1. **Planning Agent**: [Create New GPT](https://chatgpt.com/create) → Copy text from `fada_planning_agent.system.prompt.md` → Paste in Instructions → Save as "My FADA Planning"
2. **Analytics Agent**: [Create New GPT](https://chatgpt.com/create) → Copy text from `fada_analytics_agent.system.prompt.md` → Paste in Instructions → Save as "My FADA Analytics"
3. **Important**: Upload `fada_shared_config.json` to BOTH GPTs under Knowledge

### 🧠 Claude (Most Powerful)
1. Go to [Claude Projects](https://claude.ai/projects) → Create "FADA Planning" project
2. Copy contents of `fada_planning_agent.system.prompt.md` → Paste as Custom Instructions
3. Create another project "FADA Analytics" with `fada_analytics_agent.system.prompt.md`
4. Upload `fada_shared_config.json` to both projects

### 🌟 Mistral (Free Option)
1. Open [Mistral Chat](https://chat.mistral.ai) → Click your profile → "Custom Agents"
2. Create "FADA Planning" → Paste planning agent prompt → Save
3. Create "FADA Analytics" → Paste analytics agent prompt → Save
4. Upload the shared config file to both agents

### 💻 Self-Host (Maximum Privacy)
1. Install [Ollama](https://ollama.ai) and [Open WebUI](https://docs.openwebui.com)
2. Download a model: `ollama pull llama3.1:8b` (or larger if you have the space)
3. In Open WebUI → Settings → Models → Create two custom models
4. Paste the agent prompts and upload the config file
5. Your data never leaves your computer!

### 💡 Tips for Success
- Always upload `fada_shared_config.json` - it's required for security
- Start with Planning Agent if you're new to FADA
- Save your knowledge base file after each session
- Test with the example family data first

### ✅ Test Your Setup
1. Open your Planning Agent and say: "Hi, I need help with my finances"
2. It should start a friendly onboarding conversation
3. After creating a profile, ask it to "show_kb" - it should generate a downloadable file
4. Take that file to your Analytics Agent and upload it
5. Ask Analytics: "Analyze my financial situation" - it should provide detailed insights

### 🛠️ For Developers & Advanced Setup

Need more control? Want to understand the architecture? 

**→ See the [Developer Guide](developer_guide.md)** for detailed setup instructions, technical architecture, and implementation details.

## How the Agents Work Together

1. **Start with Planning Agent** for:
   - Initial profile creation
   - Goal setting and prioritization
   - Budget design
   - Getting actionable advice
   - Regular check-ins and updates

2. **Switch to Analytics Agent** for:
   - Detailed calculations (loans, investments)
   - Document analysis (bills, statements)
   - Financial forecasting
   - Data visualizations
   - Complex optimization problems

3. **Share your profile** between agents:
   - Planning Agent creates and updates your knowledge base
   - Analytics Agent reads and enhances it with calculations
   - Both use the same secure data format

## Privacy & Security

- **Your Data, Your Control**: All financial data stays in files you control
- **No Cloud Storage**: Nothing is saved on servers
- **EU AI Act Compliant**: Built with the highest privacy standards
- **Open Source**: Fully transparent - see exactly how it works

## Open Source

FADA is released under the MIT License, making it free for everyone to use, modify, and share. This aligns with our mission to democratize financial planning for all families.

---

*Built with ❤️ by [Modular Earth](https://www.linkedin.com/company/modular-earth) to help working families thrive*
