# FADA - Your Family's Financial Assistant 🤝💰

**AI financial guidance that actually works for working families**

FADA (Financial Assistant for Data Analytics) is your personal AI financial coach, built specifically for families who work hard but struggle to get ahead financially. No fancy jargon, no sales pitches, just practical help that fits your real life.

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

## How to Set Up FADA

FADA works on multiple AI platforms. Choose the one that works best for you:

### 🤖 OpenAI Custom GPTs

**Planning Agent Setup:**
1. Go to [chatgpt.com/create](https://chatgpt.com/create) and sign in
2. Click "Create a GPT" 
3. In the Configure tab, paste the system prompt from `fada_planning_agent.system.prompt.md`
4. Upload `fada_shared_config.json` as a knowledge file
5. Name your GPT "FADA Planning Agent" and save it

**Analytics Agent Setup:**
1. Create another GPT following the same process
2. Use the system prompt from `fada_analytics_agent.system.prompt.md`
3. Upload `fada_shared_config.json` as a knowledge file
4. Name it "FADA Analytics Agent" and save it

### 🧠 Anthropic Claude Projects

**Planning Agent Setup:**
1. Go to [console.anthropic.com](https://console.anthropic.com) and create a new project
2. Name it "FADA Planning"
3. Upload `fada_planning_agent.system.prompt.md` as the system prompt
4. Add `fada_shared_config.json` as a project knowledge file

**Analytics Agent Setup:**
1. Create another project named "FADA Analytics"
2. Upload `fada_analytics_agent.system.prompt.md` as the system prompt
3. Add `fada_shared_config.json` to project knowledge

### 🌟 Mistral AI Le Chat Pro

**Planning Agent Setup:**
1. Go to [chat.mistral.ai](https://chat.mistral.ai) and sign in
2. Create a new custom agent named "FADA Planning"
3. Paste the system prompt from `fada_planning_agent.system.prompt.md`
4. Upload `fada_shared_config.json` as reference

**Analytics Agent Setup:**
1. Create another agent named "FADA Analytics"
2. Use `fada_analytics_agent.system.prompt.md` as the prompt
3. Enable web search and code execution
4. Upload the shared config as reference

### 🏠 Local Setup with Ollama

**Both Agents Setup:**
1. Install OpenWebUI and Ollama on your computer
2. Download a capable model (like Llama 3.1 or Mistral)
3. In OpenWebUI, create two custom models:
   - FADA Planning: Use `fada_planning_agent.system.prompt.md`
   - FADA Analytics: Use `fada_analytics_agent.system.prompt.md`
4. Upload `fada_shared_config.json` to both as reference

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

## Technical Details

- **Planning Agent**: ~4,400 characters (fits all platforms)
- **Analytics Agent**: ~5,000 characters (fits all platforms)
- **Shared Config**: Contains security protocols, data schema, and compliance standards
- **Architecture**: Modular design for easy maintenance and updates

# Why I chose the MIT License
This license aligns with Modular Earth's mission to support social good through open-source AI-driven applications, and our commitment to accessibility, privacy, trust, and minimizing costs.

1. **Permissive Use**: The MIT License is one of the most permissive licenses, allowing for the software to be used, modified, and distributed freely, even for commercial purposes. This aligns well with Modular Earth's goal of making wealth accessible and supporting a wide range of uses without restrictive conditions.

2. **Simplicity and Clarity**: The MIT License is short and straightforward, making it easy for users to understand their rights and obligations. This simplicity can help ensure broader adoption and use of the financial assistant.

3. **Compatibility**: The MIT License is compatible with many other licenses, which can be beneficial if the financial assistant needs to be integrated with other software or libraries that have different licensing terms.

4. **Community Trust**: The MIT License is widely recognized and trusted in the open-source community. Using a well-known and respected license can help build trust with users and contributors.

5. **Minimal Restrictions**: The only significant requirement of the MIT License is that the original copyright and permission notice be included in all copies or substantial portions of the software. This minimal restriction supports Modular Earth's principles of minimizing costs and maximizing accessibility.

The MIT License effectively supports Modular Earth's mission and principles. It allows this financial assistant to be accessible to all.
