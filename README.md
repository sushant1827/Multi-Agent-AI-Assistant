# Multi-Agent-AI-Assistant

## Overview

This repository contains a sophisticated multi-agent system built on n8n workflow automation platform. The system utilizes a "Supervisor Agent" architecture that orchestrates specialized sub-agents to handle different types of tasks. Each agent is designed with specific capabilities to work together as an integrated AI assistant system.

## Architecture

The system follows a hub-and-spoke architecture:

- **Supervisor Agent**: The central orchestrator that delegates tasks to specialized agents
- **Sub-Agents**: Specialized workflows for specific domains:
  - Calendar Agent
  - Contact Agent
  - Email Agent
  - Content Creator

## Components

### Supervisor Agent

The Supervisor Agent (`Supervisor_Agent.json`) acts as the system's brain, receiving user queries and intelligently routing them to the appropriate specialized agent. It:

- Receives user chat messages
- Uses GPT-4o to analyze requests
- Maintains conversation context through memory buffer
- Orchestrates task delegation and execution flow
- Accesses multiple tools including:
  - Calculator
  - Web Search
  - Knowledge Base (Pinecone vector database)
  - Email, Contact, Calendar and Content Creator sub-agents
 
<img width="920" alt="image" src="https://github.com/user-attachments/assets/9cb2aa46-7819-42eb-9340-433fe88f029f" />

### Calendar Agent

The Calendar Agent (`Calendar_Agent.json`) manages all calendar-related operations:

- Creates new calendar events
- Retrieves existing events
- Processes date/time queries
- Works with Google Calendar integration

<img width="662" alt="image" src="https://github.com/user-attachments/assets/a3b7849d-ca64-4e77-8b6e-5097ef00a7f0" />

### Contact Agent

The Contact Agent (`Contact_Agent.json`) handles contact management tasks:

- Creates new contacts
- Updates existing contact information
- Searches for contacts
- Integrates with Google Contacts

### Email Agent

The Email Agent (`Email_Agent.json`) manages email communications:

- Sends new emails
- Retrieves unread emails
- Replies to existing email threads
- Works with Gmail integration

<img width="697" alt="image" src="https://github.com/user-attachments/assets/0875d555-2fee-4578-846a-beb5667b455c" />

### Content Creator

The Content Creator (`Content_Creator.json`) generates various content types:

- Creates SEO-friendly content
- Generates creative text
- Produces titles, descriptions, and articles
- Optimizes content for different platforms

<img width="543" alt="image" src="https://github.com/user-attachments/assets/42ff5ef9-1fb1-4824-afcf-74ad5456f386" />

## Usage

1. **Starting a conversation:**
   - Interact with the system through the n8n chat interface
   - Send messages to the "When chat message received" node in the Supervisor Agent

2. **Example queries:**
   - "What events do I have on April 14?"
   - "Update Tasu's email address to tasu.sush@test.com"
   - "Reply to Sushant about the project progress"
   - "Generate 10 YouTube title ideas for a tutorial on AI agents in n8n"

3. **Advanced features:**
   - The system can chain multiple agents together for complex tasks
   - Knowledge base queries use vector search for accurate information retrieval
   - Web search integration provides up-to-date information

## Customization

You can extend this system by:

1. **Creating new specialized agents:**
   - Duplicate an existing agent JSON file
   - Modify its tools and capabilities
   - Connect it to the Supervisor Agent

2. **Enhancing the Knowledge Base:**
   - Add more documents to the Pinecone vector database
   - Improve embedding quality by adjusting parameters

3. **Customizing system messages:**
   - Edit the system prompts in each agent to specialize their behavior

## Troubleshooting

Common issues and solutions:

- **Workflow execution errors:** Check API key validity and permissions
- **Agent coordination issues:** Verify the connections between Supervisor and sub-agents
- **Authentication problems:** Ensure OAuth permissions are properly configured

---
