# WatsonCrewAi

A simple multi-agent system using [CrewAI](https://github.com/joaomdmoura/crewAI) and IBM's [Watsonx](https://www.ibm.com/watsonx) to automate AI/quantum computing research and generate keynote speeches.

## Overview

This project demonstrates the use of two cooperating agents:
- **Senior AI Researcher**: Searches the web for promising research in the field of AI and quantum computing. Uses `SerperDevTool` for internet access.
- **Senior Speech Writer**: Takes the findings from the researcher and drafts an engaging, witty keynote speech on quantum computing.

The agents are powered by models hosted on IBM Watsonx:
- `meta-llama/llama-3-70b-instruct` for primary text generation
- `ibm-mistralai/merlinite-7b` for function calling capabilities

## Prerequisites

- Python 3.10+
- An IBM Cloud / Watsonx account and API key
- A [Serper.dev](https://serper.dev/) account and API key

## Setup

1. **Install Dependencies**
   Ensure you have the required libraries installed:
   ```bash
   pip install crewai langchain-ibm
   ```

2. **Environment Variables**
   The script relies on several API keys. In `agent.py`, make sure to provide valid keys:
   - `WATSONX_APIKEY`: Your IBM Cloud API key.
   - `SERPER_API_KEY`: Your Serper.dev API key for Google Search integration.

   *(Warning: Avoid committing sensitive API keys to version control. It is recommended to use a `.env` file in production.)*

## Usage

Run the main agent script:

```bash
python agent.py
```

### Expected Outputs

The script runs the crew and saves the results to two text files in the project directory:
- `task1output.txt`: A detailed bullet point summary of 5 examples of promising research found by the Researcher agent.
- `task2output.txt`: The final engaging keynote speech written by the Writer agent.
