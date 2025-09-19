# Competitive Analysis Agent

Below is the recommended setup for running and inspecting the competitive analysis deep agent example

## UI Setup

To visualize and interact with the competitive analysis agent, we will be using the [deep-agents-ui](https://github.com/langchain-ai/deep-agents-ui) repo.

1. In a seperate directory/terminal, clone the repo and install the requirements

```bash
git clone https://github.com/langchain-ai/deep-agents-ui.git
cd deep-agents-ui
```

2. Create a `.env.local` file with the following environment variables

```env
NEXT_PUBLIC_DEPLOYMENT_URL="http://127.0.0.1:2024"
NEXT_PUBLIC_AGENT_ID=competitive_analysis_agent
```

3. Install dependencies and launch the server

```bash
npm install
npm run dev
```

Open the interface on http://localhost:3000

## Agent Setup

To run the agent, we will be using the [LangGraph Platform](https://docs.langchain.com/langgraph-platform)

1. Clone this repo, navigate to the example, and install the requirements

```bash
git clone https://github.com/ALucek/deep-agents-walkthrough.git
cd deep-agents-walkthrough/competitive_analysis_agent
uv sync
```

2. Create a `.env` file with the following environment variables

```env
TAVILY_API_KEY=<your_api_key_here>
OPENAI_API_KEY=<your_api_key_here>
LANGSMITH_API_KEY=<your_api_key_here>
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_PROJECT=deep_competitive_analysis
```

3. Launch a local LangGraph platform server 

```bash
uv run langgraph dev
```

The competitive analysis agent will now be running on the local LangGraph server, and connected to the deep-agents-ui frontend.

_Note: There is no persistent file storage system included. All data, conversations, and files are cleared when the frontend is closed._ 