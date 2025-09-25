# FADA Universal - Financial Assistant & Data Analysis for All Families

## Overview

FADA (Financial Assistant & Data Analysis) is a free, open-source AI agent designed to democratize financial planning and help working-class families build wealth. Unlike traditional financial advisors that often exclude those who need help most, FADA provides personalized, actionable financial guidance to families regardless of their economic status.

## Mission

FADA exists to create financial balance and bend the economic system toward justice for families who are:
- Working paycheck to paycheck
- Managing multiple debts
- Time-starved from caring for family while working
- Limited to simple investment options
- Navigating economic uncertainty
- Often excluded from traditional financial services

## How It Works

### Knowledge-Based Architecture

FADA uses a personalized knowledge base (KB) approach where each user's financial information, goals, and constraints are stored in a structured JSON format. This allows FADA to:

1. **Maintain Context**: Remember your financial situation across sessions
2. **Provide Personalized Advice**: Tailor recommendations to your specific needs
3. **Track Progress**: Monitor improvements over time
4. **Protect Privacy**: Keep your data in a format you control

### Two Ways to Start

#### Option 1: Provide Your Configuration File
If you already have a FADA knowledge base file (`.json`), simply provide it when starting a session. FADA will load your profile and continue where you left off.

#### Option 2: Interactive Onboarding
New users can go through a guided onboarding process where FADA asks questions to build your personalized knowledge base. This takes about 10-15 minutes and covers:
- Basic profile information
- Income sources
- Major expenses
- Debt overview
- Savings and goals
- Time availability and preferences

## Implementation Guide

### For Anthropic Claude (Custom Projects)

1. Create a new Claude Project
2. Upload the system prompt: `fada_universal.system.prompt.md`
3. Add the knowledge base template: `knowledge_base_template.json`
4. (Optional) Upload example knowledge base files for reference
5. Start conversations by either:
   - Uploading your KB file
   - Saying "I'm new and need help creating my financial profile"

### For OpenAI Custom GPTs

1. Create a new Custom GPT
2. Set the Instructions using content from `fada_universal.system.prompt.md`
3. Upload knowledge files:
   - `knowledge_base_template.json`
   - Example knowledge base files for reference
4. Enable Code Interpreter for calculations
5. Configure to accept file uploads

### For Mistral Le Chat Pro

1. Create a new Custom Agent
2. Set the system prompt from `fada_universal.system.prompt.md`
3. Enable web search and code execution capabilities
4. Upload template files as reference

## File Structure

```
financial-assistant-for-families/
├── README.md                         # Main project introduction
├── developer_guide.md                # This implementation guide
├── fada_universal.system.prompt.md   # Main AI agent instructions
├── knowledge_base_template.json      # Blank template for new users
├── example_struggling_family_kb.json # Example KB (for AI bias education)
├── financial_assistant.system.prompt.md # Original version (deprecated)
└── LICENSE                          # MIT License
```

## Knowledge Base Structure

The KB captures comprehensive financial information in these categories:

### 1. Profile
- Personal information
- Family members
- Employment status
- Income sources

### 2. Financial Snapshot
- Total income and assets
- Liabilities and net worth
- Emergency fund status

### 3. Accounts
- Banking accounts
- Investment accounts
- Business accounts

### 4. Debts
- Types and balances
- Interest rates
- Payment priorities

### 5. Monthly Budget
- Income breakdown
- Fixed expenses
- Variable expenses
- Debt payments
- Savings/investments

### 6. Financial Goals
- Immediate needs
- Short-term (< 1 year)
- Medium-term (1-3 years)
- Long-term (3+ years)

### 7. Preferences
- Risk tolerance
- Time availability
- Primary concerns
- Values and constraints

## Usage Examples

### First Time User
```
User: "Hi, I need help with my finances but don't know where to start."
FADA: "Welcome to FADA! I'm here to help you build a personalized financial roadmap..."
[Begins onboarding process]
```

### Returning User
```
User: [Uploads their_name_kb.json]
FADA: "Welcome back! I've loaded your financial profile. Since our last session..."
[Provides updates and recommendations]
```

### Specific Questions
```
User: "Should I pay off my credit card or save for emergencies first?"
FADA: [Analyzes user's KB and provides personalized recommendation based on their situation]
```

## Privacy and Security

- **Local Control**: Your KB file stays with you
- **No Cloud Storage**: FADA doesn't store your data between sessions
- **Transparent Format**: JSON is human-readable - you can see exactly what's stored
- **Update Control**: You decide when and what to update

## Contributing

FADA is open-source and welcomes contributions! Areas for improvement:
- Additional language support
- More detailed investment guidance
- Integration with financial APIs
- Mobile-friendly interfaces
- Community resource databases

## Support

For questions or issues:
- Review example files for guidance
- Check the template structure
- Ensure your JSON is valid (use a JSON validator)
- Start with basic information and add detail over time

## License

This project is released under an open-source license to ensure it remains free and accessible to all families who need financial assistance.

---

*Remember: FADA exists to level the playing field and help working families thrive despite systemic challenges. Every interaction should move you closer to financial security and peace of mind.*