## 🌡️🌞🌦️Agentic AI Weather Assistant using Amazon Bedrock🌩️🌤️🌪️

An end-to-end **agentic AI system** built with **Amazon Bedrock** and **Claude 4.5 Sonnet** that interprets flexible user input, dynamically generates API calls, executes real-world HTTP requests, and transforms structured weather data into actionable insights.

This project demonstrates how modern AI systems move beyond static chat responses into **autonomous, tool-using agents** capable of reasoning, planning, acting, and delivering results.

---

## 🌍 Why This Project Matters

Modern AI systems are evolving beyond static chat interfaces and simple text generation into autonomous, tool-using agents that reason across contexts, orchestrate multi-step workflows, and execute actions within distributed, cloud-native environments.

This project demonstrates:

- 🧠 LLM-driven reasoning using Claude 4.5 Sonnet via Bedrock 
- 🔗 Real-world API integration (National Weather Service)
- ⚙️ Multi-step orchestration (Points API → Forecast API → AI summary processing)
- 📊 Structured JSON data parsing and transformation
- 🔐 Secure cloud integration using AWS IAM and Bedrock 🌐 Cloud-native AI integration with IAM-secured access

Rather than hardcoding logic (such as fixed weather endpoints or predefined coordinates), the system dynamically:

- Interprets ambiguous user input (e.g., “National park near Homestead in Florida”)
- Determines appropriate geographic coordinates
- Identifies the correct National Weather Service API endpoints
- Generates valid, context-specific API URLs
- Orchestrates sequential tool calls (Points API → Forecast API)
- Extracts relevant forecast data from structured JSON responses
- Converts raw data into clear, context-aware, human-readable summaries

This architecture pattern scales beyond weather and applies to: This architecture pattern generalizes to:

- Travel planning agents
- Operations automation systems
- Financial data analysis
- Monitoring systems and alerting tools
- Multi-tool AI orchestration platforms

It demonstrates the shift from “LLM responses” to AI-powered systems that take action.
It represents a shift from “LLM prompt demos” to **production-oriented AI systems design**.

---

## 📌 Project Overview

This application implements a complete agentic workflow:

## User Input → AI Planning → API Execution → AI Processing → Response

The system exists in two interfaces:

- 💻 Command-Line Agent (`weather_agent_cli.py`)
- 🌐 Streamlit Web Application (`weather_agent_web.py`)

Both versions share identical agent logic and architecture.

---

## 🏗 Architecture

<img width="1002" height="922" alt="image" src="https://github.com/user-attachments/assets/07bd3717-fbe0-4fcf-8ce0-e26899d1eba9" />

### Workflow Breakdown

1. **User Input**
   - Accepts city names, ZIP codes, descriptive text, or coordinates.

2. **AI Planning (Claude via Bedrock)**
   - Determines approximate latitude/longitude.
   - Generates NWS Points API URL dynamically.

3. **Points API Call**
   - Retrieves forecast office and grid data.

4. **Forecast API Call**
   - Retrieves detailed weather forecast JSON.

5. **AI Processing**
   - Claude analyzes raw JSON and creates a structured weather summary.

6. **Response**
   - CLI output or interactive Streamlit display.

---

## ⚙️ Environment Setup

### Prerequisites

- Python 3.7+
- AWS CLI v2
- Amazon Bedrock access (`us-west-2`)
- Claude 4.5 Sonnet model access enabled
- IAM permissions:
  - `bedrock:InvokeModel`
  - `bedrock:Converse`
  - `bedrock:ListFoundationModels`
  - `sts:GetCallerIdentity`

---

### 🐍 Create Project Directory & Virtual Environment

```bash
mkdir agentic-ai-workshop
cd agentic-ai-workshop
python -m venv .venv
```

Activate environment (Windows):

```
.\.venv\Scripts\activate
```

## 📦 Install Dependencies

```
pip install boto3>=1.34.0 streamlit>=1.28.0 requests>=2.31.0 Pillow>=10.0.0
```

## 🔐 Configure AWS Credentials (PowerShell Example)

```
$env:AWS_ACCESS_KEY_ID="YOUR_KEY"
$env:AWS_SECRET_ACCESS_KEY="YOUR_SECRET"
$env:AWS_SESSION_TOKEN="YOUR_SESSION_TOKEN_IF_PROVIDED"
$env:AWS_DEFAULT_REGION="us-west-2"
```

Verify setup:

```
aws sts get-caller-identity
```

---

## 💻 Running the Command-Line Agent

```
python weather_agent_cli.py
```

Example Inputs

- Seattle
- 90210
- New York City
- Largest City in California
- National park near Homestead in Florida

The CLI version prints each step of the agentic workflow in real time.

---

## 🌐 Running the Web Application

```
streamlit run weather_agent_web.py
```

Open the local URL displayed in the terminal (typically http://localhost:8501).

Web Features

- Step-by-step visualization of agent workflow
- Expandable raw JSON inspection
- Real-time status tracking
- Interactive user interface
- Clean separation of reasoning and execution phases

---

## 🧠 Agentic AI Patterns Demonstrated

This project highlights reusable production patterns:

- AI-driven tool selection and API generation
- Multi-step orchestration logic
- Structured data extraction and transformation
- Modular Python design
- Separation of interface and core agent logic
- Secure cloud-native model invocation via Bedrock

---

## 🛠 Technologies Used

- Amazon Bedrock
- Claude 4.5 Sonnet
- Python
- Boto3 (AWS SDK for Python)
- Streamlit
- National Weather Service API
- AWS IAM
- AWS CLI

---

## 📁 Project Structure

```
agentic-ai-workshop/
│
├── weather_agent_cli.py
├── weather_agent_web.py
├── .venv/
├── images/
│   └── architecture.png
└── README.md
```

---

## 🙏🏽 Acknowledgment ☺️

This project was completed with mentorship and implementation guidance from **Maurice J. Colon**, who assisted with environment configuration, dependency setup, and AWS IAM/Bedrock integration.

Original workshop developed by:

Ramakrishna Natarajan  
Sr. Partner Solutions Architect, AWS

---

## 🗝️ Key Takeaway 🚀

This project demonstrates how to design and deploy an AI system that:

- Reasons
- Plans
- Executes
- Processes structured data
- Delivers meaningful results

It reflects the emerging pattern of tool-using AI agents deployed in cloud environments, bridging large language models with real-world systems.







