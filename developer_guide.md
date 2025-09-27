# FADA Developer Guide 🚀

**Building AI financial assistants that actually help working families**

## What is FADA?

FADA (Financial Assistant & Data Analytics) is an open-source multi-agent AI system that provides personalized financial guidance through a knowledge base architecture. The system features two specialized agents - one for planning and onboarding, another for analytics and calculations - coordinated by a shared configuration that ensures security, compliance, and consistent data handling.

## Technical Architecture

FADA uses a multi-agent architecture with:
- **Two Specialized Agents**: Planning Agent for onboarding/goals, Analytics Agent for calculations/analysis
- **Shared Configuration**: Central config file ensuring security, compliance, and coordination
- **Knowledge Base System**: JSON-based storage with version 2.0 schema
- **EU AI Act Compliance**: Built-in security guardrails and data protection
- **Platform Adaptability**: Automatic detection and adaptation to different AI platforms
- **Agent Coordination**: Defined handoff protocols for seamless user experience

## Repository Structure

```
financial-assistant-for-families/
├── README.md                           # User-facing introduction
├── developer_guide.md                  # This file - technical setup
├── fada_planning_agent.system.prompt.md # Planning & onboarding agent
├── fada_analytics_agent.system.prompt.md # Analytics & calculations agent
├── fada_shared_config.json             # Central configuration for both agents
├── knowledge_base_template.json         # Blank template for new users
├── knowledge_base_example.json          # Example with real family data
└── LICENSE                             # MIT License
```

## Core Architecture

### Multi-Agent System

FADA uses two specialized agents coordinated by a shared configuration:

#### **FADA Planning Agent**
- **Purpose**: Onboarding, goal setting, and financial planning
- **Capabilities**: Profile creation, budget design, debt strategies, behavioral coaching
- **User Interaction**: Conversational onboarding in ~15 minutes
- **Output**: Complete knowledge base files and personalized financial plans

#### **FADA Analytics Agent**  
- **Purpose**: Calculations, forecasting, and data analysis
- **Capabilities**: Loan analysis, investment projections, document intelligence, optimization
- **User Interaction**: Process uploaded data, answer complex financial questions
- **Output**: Detailed calculations, visualizations, and actionable insights

#### **Shared Configuration (`fada_shared_config.json`)**
The central configuration file that:
- **Defines Security Guardrails**: EU AI Act compliance, data protection rules
- **Standardizes Data Format**: Knowledge base schema v2.0
- **Enables Platform Adaptation**: Auto-detection and feature adjustment
- **Coordinates Agents**: Handoff protocols and shared commands
- **Ensures Compliance**: Regulatory and professional standards

### Knowledge Base System
FADA uses a JSON-based knowledge base (v2.0) that stores:

- **Metadata**: Version, timestamps, platform info, agent tracking
- **Profile**: Family members, employment, income (with privacy protections)
- **Financial Snapshot**: Assets, liabilities, ratios, key metrics
- **Accounts**: Banking, investments, other assets
- **Debts**: All debts with rates, balances, payoff strategies
- **Budget**: Detailed monthly income and expense breakdown
- **Goals**: Immediate, short-term, medium-term, and long-term objectives
- **Analysis History**: Past recommendations and findings
- **Preferences**: Risk tolerance, values, communication style

### System Flow
1. **Agent Selection**: User chooses Planning (new users) or Analytics (existing KB)
2. **Configuration Load**: Agent loads `fada_shared_config.json` first
3. **Data Input**: Interactive onboarding or KB file upload
4. **Processing**: Agent-specific analysis following security guardrails
5. **Coordination**: Seamless handoff between agents when needed
6. **Output**: Updated KB, calculations, or recommendations

## Implementation Options

### For Anthropic Claude (Recommended)

**Setting up the Multi-Agent System:**

1. **Create Two Claude Projects** (one for each agent):
   - Project 1: "FADA Planning Agent"
   - Project 2: "FADA Analytics Agent"

2. **For Planning Agent Project**:
   - Set `fada_planning_agent.system.prompt.md` as the system instruction
   - Upload `fada_shared_config.json` as project knowledge
   - Upload `knowledge_base_template.json` and `knowledge_base_example.json`
   - Enable artifact generation for KB file creation

3. **For Analytics Agent Project**:
   - Set `fada_analytics_agent.system.prompt.md` as the system instruction
   - Upload `fada_shared_config.json` as project knowledge
   - Upload template files for reference
   - Enable code execution for calculations

4. **User Workflow**:
   - New users start with Planning Agent for onboarding
   - Planning Agent creates KB file as downloadable artifact
   - Users switch to Analytics Agent with their KB for analysis
   - Seamless handoff via shared KB format

### For OpenAI Custom GPTs

**Setting up the Multi-Agent System:**

1. **Create Two Custom GPTs**:
   - GPT 1: "FADA Planning Coach"
   - GPT 2: "FADA Analytics Expert"

2. **For Planning Coach GPT**:
   - Copy instructions from `fada_planning_agent.system.prompt.md`
   - Upload all files: shared config, templates, and example
   - Enable file downloads for KB generation
   - Set conversation starters for onboarding flow

3. **For Analytics Expert GPT**:
   - Copy instructions from `fada_analytics_agent.system.prompt.md`
   - Upload all reference files
   - Enable Code Interpreter for calculations
   - Configure to accept KB file uploads

4. **Important Notes**:
   - GPTs have character limits - may need to summarize prompts
   - Ensure both GPTs reference the shared config
   - Test handoff between GPTs with example KB

### For Mistral Le Chat Pro

**Setting up the Multi-Agent System:**

1. **Create Two Custom Agents**:
   - Agent 1: "FADA Planning Assistant"
   - Agent 2: "FADA Analytics Assistant"

2. **For Both Agents**:
   - Upload `fada_shared_config.json` as primary reference
   - Enable code execution for calculations
   - Enable web search for real-time data
   - Set respective system prompts

3. **Configuration Tips**:
   - Leverage web search for current financial rates
   - Use code execution for complex calculations
   - Ensure multi-language support if needed
   - Test KB file handling between agents

### For OpenWebUI with Ollama

**Setting up the Multi-Agent System:**

1. **Local Setup**:
   - Install OpenWebUI and Ollama
   - Download models with strong reasoning (Llama 3.1 70B+ recommended)
   - Ensure sufficient RAM for context windows

2. **Create Two Model Configurations**:
   - Config 1: Planning Agent with `fada_planning_agent.system.prompt.md`
   - Config 2: Analytics Agent with `fada_analytics_agent.system.prompt.md`

3. **Shared Configuration**:
   - Store `fada_shared_config.json` in accessible location
   - Configure both models to reference it
   - Set up file system access for KB files

4. **Privacy Advantages**:
   - Complete local processing
   - No data leaves your system
   - Full control over model parameters
   - Ideal for sensitive financial data

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

## Agent Coordination & Handoff

### How Agents Work Together

The multi-agent system ensures seamless user experience through:

#### **Planning to Analytics Handoff**
1. Planning Agent completes onboarding/update
2. Generates complete KB file with all required fields
3. Provides summary of user's situation and key questions
4. User downloads KB and uploads to Analytics Agent
5. Analytics Agent reads context and continues conversation

#### **Analytics to Planning Handoff**
1. Analytics Agent identifies need for plan updates
2. Exports enhanced KB with new calculations/insights
3. Highlights findings requiring goal adjustments
4. User returns to Planning Agent with updated KB
5. Planning Agent integrates findings into revised plan

#### **Shared Commands**
Both agents understand these commands:
- `show_kb` - Generate current knowledge base file
- `update_snapshot` - Recalculate all financial metrics
- `create_report` - Generate comprehensive analysis
- `check_progress` - Compare to previous reviews
- `export_data` - Prepare downloadable files

### Maintaining Context

The shared configuration ensures:
- **Consistent Data Format**: Both agents use same KB schema
- **Unified Security**: Same privacy rules apply everywhere
- **Platform Awareness**: Agents adapt to available features
- **Quality Standards**: Same calculation methods and assumptions

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

## Security & Compliance

### EU AI Act Compliance

FADA implements a risk-based approach aligned with EU AI Act requirements:

#### **Prohibited Practices (Never Done)**
- No behavioral manipulation exploiting financial vulnerabilities
- No social scoring based on non-financial behavior
- No discriminatory profiling by protected characteristics
- No exploitation of children's data beyond necessary planning
- No covert surveillance of spending patterns

#### **High-Risk Data Protection**
Maximum protection for:
- **Financial Identifiers**: SSN (last 4 only), account numbers, routing numbers
- **Authentication**: No passwords, PINs, security questions stored
- **Children's Data**: First names only, no schools/medical info
- **Medical Information**: Only financial impact, not diagnoses
- **Employment Sensitive**: No discrimination indicators

#### **Transparency Requirements**
- Always disclose AI nature upfront
- Explain data usage and retention
- Allow users to skip sensitive questions
- Provide clear audit trails

### Security Guardrails

#### **Data Handling Protocols**
```
NEVER store or request:
- Full SSN (last 4 digits only if essential)
- Complete account/card numbers
- Passwords, PINs, or security answers
- Children's full names or schools
- Medical diagnoses or treatments
```

#### **Session Management**
1. **Start**: AI disclosure and data usage explanation
2. **During**: Check comfort before sensitive topics
3. **End**: Remind about secure storage practices

#### **Crisis Response**
- **Safety First**: Direct to emergency services if needed
- **Financial Crisis**: Connect to assistance programs
- **Support Resources**: Hotlines for domestic violence (1-800-799-7233), mental health (988)

### Privacy by Design

- **Local Control**: Users maintain their KB files
- **No Cloud Storage**: Data never persisted on servers
- **Minimal Collection**: Only gather what helps achieve goals
- **Progressive Disclosure**: Build trust before sensitive topics
- **Clear Boundaries**: Explicit about what's not collected

## Quick Start Guide

### Step 1: Choose Your Platform
Pick the AI platform that works best for your needs:
- **Claude Projects** (Recommended): Best for complex analysis and artifacts
- **OpenAI GPTs**: Good for interactive conversations with Code Interpreter
- **Mistral Le Chat**: Great for web research and multi-language support
- **Local Ollama**: Maximum privacy with complete local control

### Step 2: Set Up the Multi-Agent System
1. Create TWO agents/projects on your chosen platform
2. **Planning Agent Setup**:
   - Upload `fada_planning_agent.system.prompt.md` as instructions
   - Add `fada_shared_config.json` as core reference
   - Include KB templates for new user onboarding
3. **Analytics Agent Setup**:
   - Upload `fada_analytics_agent.system.prompt.md` as instructions
   - Add `fada_shared_config.json` as core reference
   - Enable calculation features (Code Interpreter, etc.)

### Step 3: Test the Workflow
- **New User Path**: Start with Planning Agent → 15-min onboarding → Download KB → Upload to Analytics
- **Existing User Path**: Upload KB to Analytics → Get analysis → Return to Planning for updates
- **Try Commands**: `show_kb`, `update_snapshot`, `create_report`

## Knowledge Base Schema v2.0

The JSON structure includes metadata and comprehensive financial data:

```json
{
  "metadata": {
    "version": "2.0",
    "last_updated": "ISO-8601 datetime",
    "platform": "string",
    "agent_updated_by": "planning|analytics"
  },
  "profile": {
    "user_name": "string (first name only)",
    "age": "number",
    "location": "city, state/country",
    "family_members": [...],
    "employment": {...}
  },
  "financial_snapshot": {
    "total_annual_income": "number",
    "monthly_take_home": "number",
    "net_worth": "number",
    "emergency_fund_months": "number",
    "debt_to_income_ratio": "number",
    "savings_rate": "number",
    "free_cash_flow": "number"
  },
  "accounts": {...},
  "debts": [...],
  "monthly_budget": {...},
  "financial_goals": {...},
  "analysis_history": [...],
  "preferences": {...}
}
```

### Key Sections Explained

**Metadata** (NEW in v2.0): Version tracking, timestamps, agent coordination
**Profile**: Family info with privacy protections (first names only)
**Financial Snapshot**: Enhanced metrics including ratios and cash flow
**Accounts**: Banking, investments, and other assets
**Debts**: All debts with rates, balances, and priority scores
**Monthly Budget**: Detailed income and expense breakdown
**Financial Goals**: Immediate, short, medium, and long-term objectives
**Analysis History** (NEW): Track recommendations and progress over time
**Preferences**: Risk tolerance, values, and communication style

## Technical Examples

### Knowledge Base Structure (v2.0)
```json
{
  "metadata": {
    "version": "2.0",
    "last_updated": "2025-09-27T10:30:00Z",
    "platform": "claude_projects",
    "agent_updated_by": "planning"
  },
  "profile": {
    "user_name": "Maria",
    "age": 35,
    "location": "Austin, TX",
    "family_members": [
      {
        "name": "Carlos",
        "relationship": "spouse",
        "age": 37,
        "income_contributor": true,
        "_privacy_note": "No full names, schools, or medical details"
      }
    ]
  },
  "financial_snapshot": {
    "total_annual_income": 75000,
    "monthly_take_home": 5200,
    "net_worth": -15000,
    "emergency_fund_months": 0.5
  }
}
```

### Agent Initialization
```python
# Both agents must load shared config first
config = load_json("fada_shared_config.json")
apply_security_guardrails(config["security_guardrails"])
set_kb_schema(config["knowledge_base_schema"])
enable_platform_adaptations(config["platform_adaptations"])
```

### Mathematical Calculations
```javascript
// Debt avalanche optimization
debts.sort((a, b) => b.interest_rate - a.interest_rate);
const extra_payment = free_cash_flow;
highest_rate_debt.payment = minimum + extra_payment;

// Emergency fund target
const monthly_expenses = calculate_total_expenses(budget);
const target_emergency = monthly_expenses * 6;
const months_to_goal = (target_emergency - current_savings) / monthly_savings;
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

### Common Multi-Agent Issues
1. **Config Not Loading**: Ensure `fada_shared_config.json` is uploaded to both agents
2. **KB Version Mismatch**: Check metadata section for schema version 2.0
3. **Agent Handoff Fails**: Verify KB file has all required fields
4. **Platform Limitations**: Some platforms may have character limits for prompts

### Debugging Tools
- **JSON Validator**: Validate KB structure against schema v2.0
- **Config Checker**: Verify shared config is properly loaded
- **Template Testing**: Use updated templates with metadata section
- **Agent Testing**: Test handoff with example KB between agents

### Multi-Agent Specific Issues
1. **Agents Not Coordinating**: 
   - Check both have same shared config version
   - Verify metadata section in KB files
   - Test shared commands like `show_kb`

2. **Data Loss Between Agents**:
   - Ensure complete KB export/import
   - Check analysis_history is preserved
   - Verify metadata timestamps

3. **Security Warnings**:
   - Review shared config security_guardrails
   - Ensure no prohibited data collection
   - Check AI disclosure is shown

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