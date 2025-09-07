# AI-Powered-Airbnb-Search-and-Execution-Workflow-MCP

This n8n workflow automates the process of searching for Airbnb listings and executing actions based on the results, orchestrated by an AI agent powered by Google's Gemini Pro. It's a powerful example of how to leverage large language models to interact with external tools in a conversational manner.

#Key Features:

Conversational Interface: The workflow is initiated through a chat interface, allowing users to specify their search criteria in natural language.
AI-Powered Tool Selection: An AI Agent, built on the LangChain framework, intelligently determines which tool to use ("airbnb search" or "airbnb execute") based on the user's request.
Dynamic Tool Parameters: The AI Agent dynamically generates the necessary parameters for the selected tool, such as the location for an Airbnb search.
Integration with External Tools: The workflow utilizes the Model Context Protocol (MCP) to connect to and execute external tools, in this case, simulated "airbnb search" and "airbnb execute" functions.
Powered by Google Gemini: The advanced language understanding and generation capabilities of the models/gemini-2.5-pro model from Google drive the AI Agent's decision-making process.

#How it Works:

Chat Trigger: The workflow begins when a user sends a message through the "When chat message received" trigger.
AI Agent Processing: The message is passed to the "AI Agent" node. This agent, configured with a system message to understand the available tools, analyzes the user's intent.
Language Model Interaction: The AI Agent interacts with the "Google Gemini Chat Model" to determine the appropriate tool and generate the required parameters.
MCP Client Tool Execution: Based on the AI's decision, the corresponding "MCP Client" tool node ("airbnb search" or "Airbnb Execute") is triggered.
The dynamically generated parameters are passed to the tool for execution.

#Nodes Used:

@n8n/n8n-nodes-langchain.chatTrigger: Initiates the workflow upon receiving a chat message.
@n8n/n8n-nodes-langchain.agent: An AI agent that uses a language model to select and execute tools.
@n8n/n8n-nodes-langchain.lmChatGoogleGemini: A node that provides access to Google's Gemini large language models.
n8n-nodes-mcp.mcpClientTool: A community node that allows n8n to act as a client to a Model Context Protocol (MCP) server, enabling interaction with external tools.
n8n-nodes-base.manualTrigger & n8n-nodes-mcp.mcpClient: These nodes appear to be part of a separate, manually triggered flow for testing the MCP client connection.

#To Use This Workflow:

Set up your n8n environment. This workflow relies on community nodes, so a self-hosted n8n instance is required.
Install the n8n-nodes-mcp community node.

#Configure Credentials:

Set up your Google Gemini API credentials.
Configure the MCP Client credentials to connect to your tool server.
Define Your Tools: Ensure that the "airbnb search" and "airbnb execute" tools are available and properly configured on your MCP server.
Import the workflow and activate it.
This workflow demonstrates a sophisticated use of n8n's AI capabilities to create a flexible and intelligent automation that can interact with external systems based on natural language commands.

#Key technologies used:

n8n: for workflow automation.
LangChain: for building the AI agent.
Google Gemini: as the large language model.
Model Context Protocol (MCP): for standardized tool interaction.
