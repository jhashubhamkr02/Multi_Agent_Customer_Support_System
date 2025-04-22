# Multi_Agent_Customer_Support_System
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Overview
This repository contains a scalable, AI-powered Multi-Agent System designed to handle customer support and query resolution for Amazon. The system leverages advanced LLM (Gemini from CrewAI) and custom tools for seamless query analysis, solution research, response creation, and escalation handling.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Objective

The goal of this project is to create a robust system that:

Analyzes customer queries.

Searches and scrapes Amazon's help resources.

Provides empathetic and actionable responses.

Escalates unresolved or sensitive cases to the appropriate channels.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Project Workflow

1. Setup the LLM
   
The system uses Gemini LLM for natural language processing.

from crewai import LLM  
gem_llm = LLM(model="gemini/gemini-1.5-flash", api_key=gemini_api_key)  


2. Define the Tools
   
The following tools were implemented to gather information and process queries:

> Search Tool: Finds relevant Amazon help articles and policies using SerperDevTool().

> Scraping Tool: Extracts information from Amazon help pages using ScrapeWebsiteTool().

> Knowledge Base Tool: Reads from a local file containing common issues and solutions (knowledge_base.txt).

3. Create the Agents
   
The system comprises the following specialized agents:

> Query Analyzer: Understands the customer's issue, identifies query type, determines urgency, and flags for escalation if required.

> Solution Researcher: Finds policies, solutions, and product details to provide a comprehensive resolution package.

> Response Coordinator: Crafts customer-friendly responses based on the researched solution.

> Escalation Specialist: Handles complex cases requiring internal coordination and monitoring.

4. Define Agent Tasks
   
Each agent was assigned specific tasks to streamline query resolution:

> Query Analyzer Task:
Analyze the main and secondary concerns.
Classify the query type and determine urgency.
> Solution Researcher Task:
Research and compile step-by-step solutions using all tools.
> Response Coordinator Task:
Draft clear and empathetic responses following Amazon’s guidelines.
> Escalation Specialist Task:
Manage sensitive cases with internal coordination and action plans.

5. Kickoff the System
The multi-agent system was initiated with a predefined user query, where each agent worked collaboratively to deliver efficient and accurate resolutions.

Technologies Used
Language Model: Gemini LLM by CrewAI
Tools:
SerperDevTool for searching articles
ScrapeWebsiteTool for web scraping
FileReadTool for local knowledge base retrieval
Languages: Python
How to Run
Clone this repository.
Set up the environment and API keys for CrewAI and search tools.
Configure the knowledge base file (knowledge_base.txt).
Execute the agents by running the main script.
Future Scope
Integrate multi-language support for global customers.
Enhance agent capabilities with additional tools.
Deploy the system as a web service for scalability.
Contributing
Contributions are welcome! Please submit a pull request for any suggestions or enhancements.

License
This project is licensed under the MIT License.
