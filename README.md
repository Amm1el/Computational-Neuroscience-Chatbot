# Computational Neuroscience Chatbot

A retrieval-augmented generation (RAG) support chatbot for **NeuroAI**, a concept platform that helps students prepare for computational neuroscience interviews. Answers come from a curated knowledge base rather than the model's training data alone, so responses stay grounded in source material.

**Demo video:** https://youtu.be/XsZQaDHMvXk

## How it works

1. The chat UI (React, Next.js App Router) sends the conversation to the `/api/chat` route.
2. The API route (Node.js) passes the latest user message to **Amazon Bedrock Knowledge Bases** through the `RetrieveAndGenerate` API.
3. Bedrock retrieves the most relevant passages from the knowledge base and generates an answer grounded in them.
4. The answer is returned to the UI.

## Tech stack

| Layer | Tools |
|---|---|
| Frontend | Next.js 14, React, Material UI |
| Backend | Next.js API routes (Node.js) |
| Retrieval and generation | Amazon Bedrock Knowledge Bases, AWS SDK for JavaScript v3 |

## Run locally

```bash
git clone https://github.com/Amm1el/Computational-Neuroscience-Chatbot.git
cd Computational-Neuroscience-Chatbot
npm install
cp .env.example .env.local   # then fill in the values
npm run dev
```

Open http://localhost:3000.

### Environment variables

| Variable | Description |
|---|---|
| `KNOWLEDGE_BASE_ID` | ID of your Amazon Bedrock knowledge base |
| `MODEL_ARN` | ARN of the Bedrock foundation model used to generate answers |

AWS credentials are read from the standard AWS credential chain (for example, `aws configure`). The client uses the `us-east-1` region.

## Author

Ammiel Bowen · [ammielbowen.com](https://ammielbowen.com) · [LinkedIn](https://www.linkedin.com/in/ammielbowen/)
