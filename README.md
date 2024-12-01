# Amazon Bedrock Converse API MCP Demo

This is a demo of Anthropic's open source MCP used with Amazon Bedrock Converse API.  This combination allows for the MCP to be used with any of the many models supported by the Converse API.

## Prerequisites

- Python 3.8+
- AWS account with Bedrock access
- AWS credentials configured locally
- SQLite database (Follow the instructions in the [MCP Quick Start Guide](https://modelcontextprotocol.io/quickstart) to set this up.)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd <project-directory>
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

## Configuration

1. Ensure AWS credentials are properly configured in `~/.aws/credentials` or via environment variables:
```bash
export AWS_ACCESS_KEY_ID=your_access_key
export AWS_SECRET_ACCESS_KEY=your_secret_key
export AWS_DEFAULT_REGION=us-west-2
```

2. The default configuration uses:
- Model: anthropic.claude-3-5-sonnet-20241022-v2:0
- Region: us-west-2
- SQLite database path: ~/test.db

## Project Structure

- `app.py`: Main application entry point and interactive loop
- `converse_agent.py`: Core agent implementation with Bedrock integration
- `converse_tools.py`: Tool management and execution system
- `mcp_client.py`: MCP (Model Control Protocol) client implementation

## Usage

1. Start the application:
```bash
python app.py
```

2. Enter prompts when prompted. The agent will:
- Process your input
- Execute any necessary tools
- Provide responses
- Maintain conversation context

3. Exit the application by typing 'quit', 'exit', 'q', or using Ctrl+C

## Key Components

### ConverseAgent
The main agent class that:
- Manages conversation flow
- Integrates with Bedrock
- Handles tool execution
- Processes responses

Reference: 
```python:converse_agent.py
startLine: 3
endLine: 109
```

### ConverseToolManager
Manages tool registration and execution:
- Tool registration with schemas
- Name sanitization
- Tool execution handling

Reference:
```python:converse_tools.py
startLine: 5
endLine: 76
```

### MCPClient
Handles communication with the MCP server:
- Tool discovery
- Tool execution
- Server connection management

Reference:
```python:mcp_client.py
startLine: 6
endLine: 48
```

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.