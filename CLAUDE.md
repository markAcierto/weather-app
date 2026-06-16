# CLAUDE AI Agent Builder for n8n

A powerful tool that enables building AI-powered workflows in n8n by simply using prompts. This project integrates Claude's AI capabilities with n8n's automation platform to create intelligent automations without complex coding.

## Overview

This project provides a seamless integration between Claude AI and n8n, allowing users to:
- Create sophisticated AI agents using natural language prompts
- Build reusable workflows that leverage n8n's extensive ecosystem of nodes
- Combine Claude's reasoning capabilities with n8n's automation features
- Develop powerful automations that can process data, make decisions, and interact with various services

## Features

### 1. Prompt-Based Workflow Creation
- Define AI agents and workflows using natural language prompts
- No coding required - just describe what you want the automation to do
- Automatic conversion of prompts into n8n workflow structures

### 2. n8n Skills Integration
- Leverage n8n's extensive collection of pre-built nodes and integrations
- Seamless connection between Claude AI and n8n services
- Support for all major n8n node types (HTTP, Database, Email, etc.)

### 3. n8n MCP Compatibility
- Full integration with n8n's Model Control Protocol
- Ability to use Claude's advanced reasoning capabilities within n8n workflows
- Support for complex multi-step AI processing

## Getting Started

### Prerequisites
1. An active n8n instance
2. Access to Claude API (or local Claude model)
3. n8n MCP plugin installed in your n8n environment

### Installation
1. Clone or download this repository
2. Install required dependencies:
   ```bash
   npm install
   ```
3. Configure your Claude API credentials
4. Set up n8n MCP connection

### Basic Usage
```yaml
# Example workflow definition using prompts
name: "Email Response Automation"
description: "Automatically analyze incoming emails and generate appropriate responses"

steps:
  - name: "Analyze Email Content"
    prompt: "Analyze the following email content for sentiment, urgency, and key information"
    
  - name: "Generate Response"
    prompt: "Based on the analysis, create a professional response that addresses the main points and maintains appropriate tone"
    
  - name: "Send Response"
    action: "send_email"
    template: "{{response}}"
```

## Core Components

### 1. Prompt Engine
The core component that interprets natural language prompts and translates them into actionable workflow steps:
- Natural language to workflow mapping
- Context-aware decision making
- Dynamic workflow generation

### 2. n8n Integration Layer
Enables seamless communication between Claude AI and n8n:
- Node execution orchestration
- Data transformation between AI and n8n formats
- Error handling and recovery mechanisms

### 3. Workflow Builder
Visual and textual workflow creation interface:
- Drag-and-drop workflow building
- Prompt-based workflow definition
- Version control for workflow templates

## Integration with n8n Skills

### Available Skills
- **HTTP Request**: Make API calls to external services
- **Database Operations**: Query and manipulate databases
- **Email Services**: Send, receive, and process emails
- **File Handling**: Read, write, and manipulate files
- **Webhook Processing**: Handle incoming webhooks
- **Data Transformation**: Process and format data

### Skill Integration Examples
```yaml
# Example: Database Integration
prompt: "Find all customers who made purchases in the last 30 days"
skill: "database_query"
query: "SELECT * FROM customers WHERE last_purchase_date > DATE_SUB(NOW(), INTERVAL 30 DAY)"
```

```yaml
# Example: Email Processing
prompt: "Analyze this email for important information and extract customer name, product, and issue description"
skill: "email_processor"
template: "Customer: {{customer_name}}, Product: {{product}}, Issue: {{issue}}"
```

## Integration with n8n MCP

### Model Control Protocol Support
- **Model Selection**: Choose between different Claude models based on requirements
- **Context Management**: Handle complex multi-turn conversations
- **Parameter Tuning**: Adjust AI parameters for specific tasks

### MCP Features
```yaml
# Example MCP configuration
mcp_config:
  model: "claude-3-opus"
  temperature: 0.7
  max_tokens: 1000
  context_window: 20000
```

## Workflow Templates

### Common Automation Patterns

#### 1. Data Processing Pipeline
```yaml
name: "Data Transformation Pipeline"
steps:
  - name: "Data Ingestion"
    prompt: "Extract data from the provided source and identify key fields"
    
  - name: "Data Validation"
    prompt: "Validate the extracted data against expected formats and constraints"
    
  - name: "Data Enrichment"
    prompt: "Enhance the data with additional information from external sources"
```

#### 2. Customer Service Automation
```yaml
name: "Customer Support Assistant"
steps:
  - name: "Query Analysis"
    prompt: "Analyze customer query to determine category, urgency, and required action"
    
  - name: "Response Generation"
    prompt: "Generate an appropriate response based on the query category and customer service guidelines"
    
  - name: "Action Execution"
    prompt: "Execute the necessary actions (ticket creation, information update, etc.)"
```

#### 3. Content Creation Workflow
```yaml
name: "Content Generation Pipeline"
steps:
  - name: "Topic Research"
    prompt: "Research and gather relevant information about the specified topic"
    
  - name: "Content Planning"
    prompt: "Create an outline for content creation based on research findings"
    
  - name: "Draft Creation"
    prompt: "Write a high-quality draft based on the outline and research"
```

## Advanced Features

### 1. Multi-Agent Collaboration
- Coordinate multiple AI agents working on different aspects of a workflow
- Enable complex decision-making processes
- Support for specialized agent roles (analyst, creator, executor)

### 2. Dynamic Workflow Adaptation
- Adjust workflows based on real-time data and feedback
- Self-improving automation systems
- Continuous learning from workflow performance

### 3. Context-Aware Processing
- Maintain context across multiple workflow steps
- Enable long-term memory for complex tasks
- Support for multi-turn conversations

## Best Practices

### Prompt Engineering
1. **Be Specific**: Clearly define the desired outcome and expected format
2. **Provide Examples**: Include sample inputs and outputs when possible
3. **Define Constraints**: Specify limitations and requirements for responses
4. **Use Clear Instructions**: Break down complex tasks into manageable steps

### Workflow Design
1. **Modular Approach**: Break complex workflows into smaller, reusable components
2. **Error Handling**: Implement robust error handling and fallback mechanisms
3. **Testing**: Test workflows with various inputs to ensure reliability
4. **Documentation**: Maintain clear documentation for each workflow component

## Troubleshooting

### Common Issues
1. **Prompt Interpretation Errors**
   - Ensure prompts are clear and unambiguous
   - Provide sufficient context in prompts
   - Test with sample data first

2. **Integration Problems**
   - Verify n8n MCP connection is established
   - Check API credentials and permissions
   - Confirm required nodes are installed and configured

3. **Performance Issues**
   - Monitor workflow execution time
   - Optimize complex prompts to reduce processing time
   - Implement caching where appropriate

## Contributing

We welcome contributions to improve this project! Please follow these guidelines:
1. Fork the repository
2. Create a feature branch
3. Commit your changes with clear messages
4. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, please open an issue in the GitHub repository or contact our support team.

## Acknowledgments

- Thanks to the n8n community for providing an excellent automation platform
- Special thanks to Claude AI for enabling powerful AI capabilities
- Recognition to all contributors who have helped build this project