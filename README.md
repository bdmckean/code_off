# Code-Off: Claude Code vs Cursor

AI Coding Assistant Comparison - Expense Tracking Application

## Presentation Materials

This repository contains technical analysis and documentation comparing two implementations of the same expense tracking application, built with different AI coding assistants.

### Documents

- **[COMPARISON.md](COMPARISON.md)** - Comprehensive side-by-side comparison
  - Architecture differences
  - Code quality metrics
  - Development time analysis
  - Prompt engineering lessons
  - Production readiness assessment
  - Cost-benefit analysis

- **[ARCHITECTURE_CLAUDE.md](ARCHITECTURE_CLAUDE.md)** - budget_claude (Flask + Claude Code)
  - Monolithic architecture
  - System diagrams
  - Performance metrics
  - Design decisions

- **[ARCHITECTURE_CURSOR.md](ARCHITECTURE_CURSOR.md)** - budget_cursor (FastAPI + Cursor)
  - Modular architecture
  - Testing infrastructure
  - Validation patterns
  - Future improvements

### The Experiment

**Objective**: Build an AI-powered expense tracking app with transaction categorization using local LLMs (Ollama + llama3.1:8b)

**Implementations**:
- `budget_claude`: Built with Claude Code (Anthropic Claude Sonnet 4.5)
- `budget_cursor`: Built with Cursor (using Claude models)

**Key Findings**:
- Claude Code: 40% faster to MVP, favored rapid iteration (monolithic structure)
- Cursor: Generated more production-ready code (modular, tested, typed)
- Both successfully integrated local LLM with comparable performance
- Local Ollama: $0/month vs cloud APIs $20-50/month
- Accuracy: 85-90% with historical context learning

### Presentation Focus

For builder community interested in:
- AI-assisted development trade-offs
- Local LLM deployment strategies
- Code quality vs development speed
- Practical prompt engineering lessons
- Production readiness assessment

### Sample Data

The `data/` directory contains anonymized sample CSV files in multiple formats for testing both applications:
- `simple_transactions.csv` - Basic 3-column format (14 rows)
- `credit_card_transactions.csv` - Credit card statement format (15 rows)
- `chase_transactions.csv` - Chase bank export format (13 rows)
- `bank_checking_transactions.csv` - Bank checking format (15 rows)

See [data/README.md](data/README.md) for detailed format descriptions.

### Source Repositories

- budget_claude: `../budget_claude/`
- budget_cursor: `../budget_cursor/`
- budget_tracing: `../budget_tracing/` (shared Langfuse monitoring)

### Technical Stack

**Both Apps**:
- Frontend: React
- Backend: Python (Flask vs FastAPI)
- LLM: Ollama with llama3.1:8b (local)
- Monitoring: Langfuse (optional)
- Container: Docker + Docker Compose

**Key Difference**: Architectural philosophy influenced by AI assistant choice
