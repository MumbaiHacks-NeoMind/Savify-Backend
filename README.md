# Financial AI System

🤖 **Intelligent Financial Analysis & Advisory System**

A comprehensive FastAPI backend that provides AI-powered financial analysis, personalized insights, and multi-domain financial advice through a unified chat interface.

---

## Demo Video Link

[YouTube Video Link](https://youtu.be/TGuGiL23uPU)

---

## Frontend Repository

Savify-Frontend: [GitHub Link](https://github.com/MumbaiHacks-NeoMind/Savify-Website.git)

---

## About Savify

### **What we plan to build**
We aim to build an *Agentic AI Financial Coaching Assistant* that learns from each user’s financial behavior and continuously adapts its advice. The platform will integrate financial data from multiple sources—bank transactions, e-wallets, gig payments, and manual entries—to provide real-time insights, personalized recommendations, and proactive alerts. At its core, the system includes five intelligent modules:

* *Finance Tracker* to monitor income, expenses, savings, liabilities, and cash flow, all displayed on a smart dashboard.
* *Analyzer & Insights Engine* to detect spending patterns, overspending triggers, recurring financial leaks, and potential saving opportunities.
* *Financial Planner* to help users create personalized financial goals and automatically generate plans for budgeting, saving, and investment.
* *Smart Tagging System* to automatically categorize expenditures such as bills, EMIs, groceries, travel, subscriptions, and flag unusual financial activity.
* *Master Agent AI* that autonomously prioritizes financial tasks like budgeting, bill reminders, EMI alerts, and nudges users for investments or savings.

Overall, we’re building a smart finance companion that not only tracks money but actively *guides, coaches, and optimizes users' financial decisions* in real-time.

## **What specific pain points it addresses**

Many individuals struggle with mismatched budgets, untracked expenses, loan burdens, and lack of financial clarity. Our AI platform solves this by giving users a clear and accurate picture of income vs. spending, highlighting unnecessary expenses, and helping manage EMIs or loans efficiently. It also addresses irregular income challenges faced by freelancers and gig workers by forecasting low-income months and suggesting financial buffers. Unlike static finance apps, our system provides personalized, dynamic, and actionable financial guidance—helping users stay disciplined with nudges, alerts, and goal trackers. Ultimately, it reduces stress around money management and helps people make smarter financial decisions effortlessly.

## **Who the target audience is**
Our primary audience includes gig workers and freelancers with fluctuating incomes, students and early professionals beginning their financial journey, and young adults seeking personalized financial discipline tools. It is also valuable for individuals in the informal sector, people managing loans or EMIs, and anyone who wants AI-powered assistance for budgeting, saving, or investment planning. Simply put, it’s built for everyday individuals who struggle to track, plan, and optimize their finances on their own.

## **Go-To-Market (GTM) Strategy & Revenue Streams**
We will launch using a freemium model, offering core finance tracking for free and premium AI-driven planning, deeper insights, and personalized investment advice under paid plans. For distribution, we’ll partner with digital banks, UPI platforms, and gig economy apps to enable easy onboarding and financial data integration. Growth will be driven through financial influencers, social media content, referral rewards, and community-building campaigns.

Revenue will primarily come from subscription plans, followed by affiliate commissions on recommended financial products like insurance, mutual funds, or credit optimization tools. Additional revenue sources include API services for fintech platforms, personalized financial coaching sessions, and potential white-label licensing to financial institutions.

---

## 🚀 Quick Start

1. Clone the repository
```bash
git clone https://github.com/Madhur-Prakash/Financial-AI-System-V2.git
cd financial_ai_system_v2
```

2. Create virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Set up environment variables
```bash
# Copy the .env.sample file to .env and fill in the required values.
```

5. Start the server
```bash
cd backend
uvicorn app:app --port 8000 --reload
```

**Alternative: Run with Docker**
```bash
# Set up .env file first, then:
docker compose up --build -d
```
---

**API Documentation**: `http://localhost:8000/docs`

## 🎯 Key Features

- **🤖 Master Agent**: Intelligent query classification and routing
- **📊 Expenditure Analysis**: Automated spending pattern analysis
- **💡 AI Insights**: Personalized financial recommendations using Groq LLM
- **🎯 Multi-Domain Advice**: Tax, investment, revenue, and general financial guidance
- **🔄 Unified API**: Single endpoint handles all query types
- **⚡ High Performance**: FastAPI with async processing

---

## 📖 Documentation

### 📚 **[Complete Documentation →](./docs/README.md)**

| Document | Description | Audience |
|----------|-------------|----------|
| **[System Overview](./docs/system-overview.md)** | High-level system capabilities and benefits | Everyone |
| **[Frontend Integration](./docs/frontend-integration.md)** | Complete integration guide with examples | Frontend Developers |
| **[API Reference](./docs/api-reference.md)** | Detailed API documentation | All Developers |
| **[Architecture Deep Dive](./docs/architecture.md)** | Technical architecture and design patterns | Backend Developers |
| **[Examples & Use Cases](./docs/examples.md)** | Real-world implementation examples | All Developers |

---

## 🔥 Quick Examples

### Simple Chat Integration
```javascript
const response = await fetch('http://localhost:8000/chat', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    message: "How can I save money on groceries?",
    user_context: "College student"
  })
});

const data = await response.json();
console.log(data.response); // AI-generated advice
console.log(data.query_type); // "insights_generation"
```

### Expenditure Analysis
```javascript
const expenses = [
  { amount: 50, category: "food", description: "Groceries", date: "2024-01-15T10:00:00" },
  { amount: 30, category: "transport", description: "Bus fare", date: "2024-01-15T08:00:00" }
];

const analysis = await fetch('http://localhost:8000/chat', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    message: "Analyze my spending patterns",
    expenditure_data: expenses
  })
});
```
---

## 🏗️ System Architecture

```
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  Frontend   │◄──►│   FastAPI    │◄──►│  Groq LLM   │
│ (Any Tech)  │    │   Backend    │    │ (AI Models) │
└─────────────┘    └──────┬───────┘    └─────────────┘
                          │
                   ┌──────▼──────┐
                   │ Master Agent│
                   │  (Router)   │
                   └──────┬──────┘
        ┌─────────────────┼─────────────────┐
        ▼                 ▼                 ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│ Expenditure  │ │   Insights   │ │  Financial   │
│   Analyzer   │ │    Agent     │ │   Advisors   │
└──────────────┘ └──────────────┘ └──────────────┘
```
---

## 🎯 Query Types Supported

| Type | Description | Example Query |
|------|-------------|---------------|
| **expenditure_analysis** | Spending pattern analysis | "Analyze my expenses" |
| **insights_generation** | Financial recommendations | "How can I save money?" |
| **tax_advice** | Tax planning and tips | "What can I deduct?" |
| **investment_advice** | Investment guidance | "Should I buy stocks?" |
| **revenue_analysis** | Income optimization | "How to increase revenue?" |
| **general_chat** | General financial questions | "What is compound interest?" |

---

## 🚀 Getting Started by Role

### 👨‍💻 **Frontend Developers**
1. **[Frontend Integration Guide](./docs/frontend-integration.md)** - Complete setup with React/JS examples
2. **[API Reference](./docs/api-reference.md)** - Endpoint documentation
3. **[Examples](./docs/examples.md)** - Real-world implementation patterns

### 🏗️ **Backend Developers** 
1. **[Architecture Deep Dive](./docs/architecture.md)** - System design and patterns
2. Explore the codebase: `backend/` directory

### 📋 **Product Managers**
1. **[System Overview](./docs/system-overview.md)** - Capabilities and benefits
2. **[Examples & Use Cases](./docs/examples.md)** - Real-world applications
3. **[API Reference](./docs/api-reference.md)** - Technical capabilities

---

## 🛠️ Technology Stack

- **Backend**: FastAPI, Python 3.8+
- **AI**: Groq LLM, LangChain
- **Validation**: Pydantic
- **Frontend**: React (example provided)
- **Deployment**: Docker, AWS, Heroku ready

---

## 📞 Support & Contributing

- **Issues**: Report bugs and feature requests
- **Documentation**: Comprehensive guides in `/docs`
- **Examples**: Working code samples included
- **API Docs**: Auto-generated at `/docs` endpoint

---

**Ready to integrate?** Start with the **[Frontend Integration Guide](./docs/frontend-integration.md)** 🚀
