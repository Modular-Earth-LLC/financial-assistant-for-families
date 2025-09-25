# FADA Developer Guide 🚀

**Building AI financial assistants that actually help working families**

## What is FADA?

FADA (Financial Assistant & Data Analytics) is an open-source AI agent system that provides personalized financial guidance through a knowledge base architecture. The system uses JSON-based data storage and mathematical modeling to deliver financial recommendations.

## Technical Architecture

FADA is built on a knowledge base system that:
- **Stores financial data** in structured JSON format
- **Performs calculations** using mathematical models
- **Provides recommendations** based on user-specific data
- **Maintains privacy** through local data storage
- **Supports multiple platforms** through adaptable system prompts

## Repository Structure

```
financial-assistant-for-families/
├── README.md                           # User-facing introduction
├── developer_guide.md                  # This file - technical setup
├── financial_assistant.system.prompt.md # Core AI agent instructions
├── knowledge_base_template.json         # Blank template for new users
├── knowledge_base_example.json          # Example with real family data
└── LICENSE                             # MIT License
```

## Core Architecture

### Knowledge Base System
FADA uses a JSON-based knowledge base that stores everything about a family's financial situation:

- **Profile**: Family members, employment, income sources
- **Financial Snapshot**: Assets, liabilities, net worth, emergency fund
- **Accounts**: Banking, investments, business accounts
- **Debts**: All debts with rates, balances, and payoff strategies
- **Budget**: Detailed monthly income and expense breakdown
- **Goals**: Immediate, short-term, medium-term, and long-term financial goals
- **Preferences**: Risk tolerance, time availability, values, constraints

### System Flow
1. **Data Input**: JSON knowledge base file or interactive onboarding
2. **Analysis Engine**: Mathematical calculations and risk assessment
3. **Recommendation Generation**: Personalized advice based on user data
4. **Progress Tracking**: Historical data updates and metric calculations
5. **Output Generation**: Structured responses and updated knowledge base

## Implementation Options

### For Anthropic Claude (Recommended)
1. Create a new Claude Project
2. Upload `financial_assistant.system.prompt.md` as the system prompt
3. Add `knowledge_base_template.json` as a reference file
4. Users can upload their KB files or start fresh

### For OpenAI Custom GPTs
1. Create a new Custom GPT
2. Copy the system prompt from `financial_assistant.system.prompt.md`
3. Upload the template and example files
4. Enable Code Interpreter for calculations
5. Configure to accept file uploads

### For Mistral Le Chat Pro
1. Create a new Custom Agent
2. Set the system prompt from `financial_assistant.system.prompt.md`
3. Enable web search and code execution
4. Upload template files as reference

### For OpenWebUI with Ollama
1. Install OpenWebUI and Ollama locally
2. Download a suitable model (Llama 3.1, Mistral, or similar)
3. Create a custom model configuration
4. Set the system prompt from `financial_assistant.system.prompt.md`
5. Upload template files as reference

## Platform-Specific Implementation Details

### ChatGPT Custom GPTs
**Best for**: Interactive conversations and calculations
**Key Features**: Code interpreter, file uploads, custom actions
**Setup Requirements**:
- OpenAI Plus subscription
- Access to GPT-4 models
- File upload capability for knowledge base

**Implementation Tips**:
- Use the Code Interpreter for financial calculations
- Upload both template and example files for reference
- Enable file uploads for user knowledge base files
- Set temperature to 0.7 for consistent responses

### Anthropic Claude Projects
**Best for**: Complex financial analysis and reasoning
**Key Features**: Advanced reasoning, large context windows, XML tags
**Setup Requirements**:
- Anthropic API access
- Claude 3.5 Sonnet or newer
- Project-based organization

**Implementation Tips**:
- Use XML tags for structured responses
- Leverage Claude's reasoning capabilities for complex analysis
- Upload template files as reference materials
- Use artifacts for downloadable reports

### Mistral AI Le Chat Pro
**Best for**: Multi-language support and web research
**Key Features**: Web search, code execution, multi-language
**Setup Requirements**:
- Mistral AI account
- Le Chat Pro subscription
- Web search capabilities

**Implementation Tips**:
- Enable web search for real-time financial data
- Use code execution for calculations
- Upload template files for reference
- Configure for multi-language support if needed

### OpenWebUI with Ollama
**Best for**: Local deployment and privacy
**Key Features**: Local processing, custom models, privacy
**Setup Requirements**:
- Local installation of OpenWebUI and Ollama
- Suitable financial model (Llama 3.1, Mistral, etc.)
- Sufficient local compute resources

**Implementation Tips**:
- Choose a model with strong reasoning capabilities
- Configure for local file access
- Set up proper model parameters
- Ensure sufficient context window size

## Key Features for Developers

### Mathematical Engine
- Debt payoff calculations with multiple strategies
- Investment projections with confidence intervals
- Budget optimization algorithms
- Risk assessment and mitigation

### Data Privacy
- No cloud storage of personal financial data
- Local JSON file control
- Transparent data structure
- User-controlled updates

### Cross-Platform Compatibility
- Works on Claude, OpenAI, Mistral, and other AI platforms
- Graceful degradation when advanced features aren't available
- Consistent user experience across platforms

## Quick Start Guide

### Step 1: Choose Your Platform
Pick the AI platform that works best for your needs:
- **Claude Projects** (Recommended): Best for complex financial analysis
- **OpenAI GPTs**: Good for interactive conversations and calculations
- **Mistral Le Chat**: Great for web research and multi-language support

### Step 2: Set Up FADA
1. Create a new project/agent on your chosen platform
2. Upload `financial_assistant.system.prompt.md` as the system prompt
3. Add `knowledge_base_template.json` as a reference file
4. (Optional) Add `knowledge_base_example.json` to see how it works

### Step 3: Test It Out
- Upload the example knowledge base file
- Ask FADA to analyze the family's financial situation
- Try different questions like "Should they pay off debt or save first?"

## Knowledge Base Schema

The JSON structure is designed to be both comprehensive and simple:

```json
{
  "profile": {
    "user_name": "string",
    "family_members": [...],
    "employment": {...}
  },
  "financial_snapshot": {
    "total_annual_income": "number",
    "net_worth": "number",
    "emergency_fund_months": "number"
  },
  "debts": [...],
  "monthly_budget": {...},
  "financial_goals": {...},
  "preferences": {...}
}
```

### Key Sections Explained

**Profile**: Who the family is, their jobs, income sources
**Financial Snapshot**: Current financial position at a glance
**Debts**: All debts with rates, balances, and payoff strategies
**Monthly Budget**: Detailed income and expense breakdown
**Financial Goals**: What they want to achieve and when
**Preferences**: How they want to approach money and investing

## Technical Examples

### Knowledge Base Validation
```json
{
  "profile": {
    "user_name": "string",
    "family_members": [{"name": "string", "relationship": "string"}]
  },
  "financial_snapshot": {
    "total_annual_income": "number",
    "net_worth": "number"
  }
}
```

### Mathematical Calculations
```javascript
// Debt payoff calculation
monthlyPayment = principal * (rate * Math.pow(1 + rate, periods)) / 
                 (Math.pow(1 + rate, periods) - 1);

// Investment projection
futureValue = presentValue * Math.pow(1 + rate, periods);
```

### System Prompt Integration
```markdown
## Analysis Framework
<analysis_framework>
  <situation_assessment>
    - Current Position: Assets, liabilities, cash flow
    - Stress Points: Immediate risks with deadlines
  </situation_assessment>
</analysis_framework>
```

## Technical Details

### Data Privacy Implementation
- **Local storage only** - No cloud data persistence
- **JSON format** - Human-readable and portable
- **User-controlled updates** - Manual data modification
- **Platform-agnostic** - Works across AI platforms

### Error Handling
- **JSON validation** - Structure validation before processing
- **Data type checking** - Numeric validation for financial calculations
- **Missing data handling** - Graceful degradation for incomplete information
- **Platform compatibility** - Feature detection and fallbacks

## Troubleshooting

### Common Development Issues
1. **JSON Schema Validation**: Ensure knowledge base matches template structure
2. **Mathematical Precision**: Use proper decimal handling for financial calculations
3. **Platform Feature Detection**: Implement graceful degradation for missing capabilities
4. **Data Type Validation**: Verify numeric inputs before calculations

### Debugging Tools
- **JSON Validator**: Validate knowledge base structure
- **Template Comparison**: Compare against `knowledge_base_template.json`
- **Example Testing**: Use `knowledge_base_example.json` for testing
- **System Prompt Review**: Check `financial_assistant.system.prompt.md` for requirements

### Platform-Specific Issues

#### ChatGPT Custom GPTs
- **File Upload Limits**: Ensure knowledge base files are under size limits
- **Code Interpreter**: Verify calculations are working correctly
- **Temperature Settings**: Adjust for consistent financial advice
- **Model Selection**: Use GPT-4 for best results

#### Anthropic Claude Projects
- **Context Window**: Ensure system prompt fits within limits
- **XML Tag Parsing**: Verify structured responses are working
- **File References**: Check that uploaded files are accessible
- **API Rate Limits**: Monitor usage for production deployments

#### Mistral Le Chat Pro
- **Web Search**: Verify search capabilities are enabled
- **Code Execution**: Test calculation functions
- **Multi-language**: Check language settings if needed
- **Model Performance**: Ensure chosen model handles financial reasoning

#### OpenWebUI with Ollama
- **Model Selection**: Choose models with strong reasoning capabilities
- **Local Resources**: Ensure sufficient RAM and compute power
- **File Access**: Verify local file system permissions
- **Model Parameters**: Tune temperature and context settings

## Contributing

### Development Areas
- **System Prompt Enhancement**: Improve AI agent instructions and capabilities
- **Mathematical Models**: Add new financial calculation methods
- **Platform Integration**: Support for additional AI platforms
- **Schema Evolution**: Extend knowledge base structure for new features
- **Testing Framework**: Automated testing for financial calculations

### Code Standards
- **JSON Schema**: Follow template structure for knowledge base files
- **Mathematical Precision**: Use proper decimal handling for financial calculations
- **Platform Compatibility**: Ensure features work across AI platforms
- **Documentation**: Update technical documentation for new features

## License

This project uses the MIT License - free to use, modify, and distribute. Perfect for helping families build wealth without restrictions.

---

*FADA exists to level the playing field and help working families thrive. Every line of code should move families closer to financial security and peace of mind.*