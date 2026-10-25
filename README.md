# n8n-ai-customer-support-triage-bot-vector-database
AI-powered customer support automation built with n8n, OpenAI, Gmail, and Pinecone to retrieve relevant policy information and prepare customer email reply drafts.


# AI Customer Support Triage Bot

An AI-powered customer support automation project built with **n8n, OpenAI, Gmail, and Pinecone**.

The project demonstrates how AI agents and retrieval-augmented generation (RAG) can help automate customer support by retrieving relevant policy information and preparing email replies for human review.

The example use case is **SOLOLIKE**, a fictional direct-to-consumer (D2C) T-shirt brand.

## Project Overview

Customer support teams frequently receive repetitive enquiries about product policies, returns, refunds, and other customer service matters.

This project explores how an AI-powered workflow can retrieve relevant information from a knowledge base, generate an appropriate response, and prepare an email draft for review.

The objective is to reduce repetitive manual work while maintaining accurate, consistent, and customer-focused communication.

## Key Features

- **Email Integration:** Uses Gmail to receive customer support emails.
- **AI-Powered Processing:** Uses an OpenAI model through an n8n AI Agent to interpret customer enquiries.
- **Knowledge Retrieval:** Uses Pinecone to search for relevant information from the SOLOLIKE policy knowledge base.
- **Context-Aware Responses:** Uses retrieved policy information to help generate relevant customer replies.
- **Email Draft Creation:** Integrates with Gmail to prepare responses as drafts.
- **Human Review:** Keeps generated replies available for review before sending.
- **Workflow Automation:** Connects the components through an n8n workflow.

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and AI Agent orchestration |
| OpenAI | Language model and text embeddings |
| Pinecone | Vector database and knowledge retrieval |
| Gmail | Customer email processing and draft creation |
| Retrieval-Augmented Generation (RAG) | Grounds responses in retrieved policy information |

## Workflow Architecture

The workflow consists of the following components:

1. **Gmail Trigger**  
   Detects incoming customer support emails.

2. **OpenAI Message Model**  
   Processes the incoming email and prepares information for subsequent workflow steps.

3. **IF Node**  
   Routes the workflow according to configured conditions.

4. **AI Agent**  
   Coordinates the customer support process and uses connected tools.

5. **Pinecone Knowledge Retrieval**  
   Searches the policy knowledge base for relevant information.

6. **HTTP Request Tool**  
   Provides an alternative approach for querying Pinecone's Documents API when the standard Pinecone Vector Store retrieval node encounters document-schema compatibility issues.

7. **Gmail Create Draft Tool**  
   Creates a customer email reply draft for human review.

8. **OpenAI Chat Model and Embeddings**  
   Support language generation and vector-based information retrieval.

**Note:** The workflow is under development. The HTTP Request approach and dynamic query handling require end-to-end validation before the complete workflow can be considered operational.

## Example Use Case

**Scenario:** A customer emails SOLOLIKE asking about its T-shirt return policy.

The intended workflow is:

1. Receive the customer's email through Gmail.
2. Identify the customer's question.
3. Search the Pinecone knowledge base for relevant policy information.
4. Use the retrieved information to prepare a suitable reply.
5. Create an email draft in Gmail.
6. Allow a human to review and send the response.

If the knowledge base does not contain the required information, the AI Agent should avoid inventing an answer and instead prepare an appropriate response indicating that the support team will assist further.

## Knowledge Base

The example knowledge base contains fictional customer support policies for SOLOLIKE, a T-shirt brand.

The documents are intended to support enquiries such as:

- Return and refund policies
- Damaged or defective products
- Required information for refund requests
- Customer support procedures
- Relevant policy exceptions

The AI Agent should use retrieved information rather than inventing policies or making unsupported promises.

## Setup and Configuration

To reproduce this project, you will need:

- An n8n instance or n8n Cloud account
- An OpenAI API account and API key
- A Pinecone account and API key
- A Pinecone index containing the relevant policy documents
- A Gmail account connected to n8n

### General Setup

1. Create your n8n workflow.
2. Configure the Gmail Trigger to receive customer support emails.
3. Connect the OpenAI model to the AI Agent.
4. Configure the Pinecone index and embeddings.
5. Connect the knowledge retrieval tool to the AI Agent.
6. Configure the Gmail Create Draft tool.
7. Add the appropriate system message and workflow instructions.
8. Test the workflow with sample customer enquiries.
9. Verify the retrieved information and generated drafts before enabling production automation.

**Important:** Pinecone index configuration, document schemas, searchable field names, API versions, and retrieval endpoints must be compatible with the selected integration.

## Security and Responsible AI

This project follows a human-review approach to customer support automation.

- API keys and credentials must be stored securely in n8n.
- Never commit API keys, passwords, access tokens, or private customer information to GitHub.
- Use fictional or anonymised customer data for demonstrations.
- Ground responses in retrieved policy information.
- Avoid unsupported claims about refunds, replacements, delivery, or other customer commitments.
- Review generated drafts before sending them to customers.

## Current Development Status

**Status: In Development**

The workflow architecture has been created, and the Pinecone Documents API has been tested successfully with a fixed search query.

Remaining work includes:

- Passing the actual customer enquiry dynamically to Pinecone.
- Validating the complete AI Agent tool-calling process.
- Confirming that retrieved policy information is used correctly.
- Testing Gmail draft creation using actual workflow inputs.
- Performing end-to-end testing with different customer enquiries.

The project will be considered complete when the entire workflow reliably retrieves relevant policy information and creates appropriate Gmail drafts.

## Future Improvements

Potential enhancements include:

- Automated classification of incoming customer emails.
- Priority-based support ticket routing.
- Sentiment and urgency detection.
- Escalation of unresolved enquiries to a human support team.
- Improved retrieval accuracy and evaluation.
- Logging and monitoring of workflow executions.
- Support for additional knowledge sources and product categories.

## Learning Outcomes

This project explores practical applications of:

- AI Agents and workflow automation
- Retrieval-Augmented Generation (RAG)
- Vector databases and semantic search
- API integrations
- Email automation
- Prompt engineering
- Human-in-the-loop AI workflows
- Troubleshooting AI integrations

## Author

**Socorro Rebelo**

Data Scientist | Microsoft IT Support Specialist | Generative AI Specialist

Interested in AI agents, workflow automation, intelligent knowledge retrieval, and practical Generative AI applications.

## Disclaimer

SOLOLIKE is a fictional brand used for demonstration and learning purposes. Its policies and customer support scenarios are illustrative and do not represent a real company's policies.
