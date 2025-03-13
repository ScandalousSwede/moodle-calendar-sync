# Moodle Calendar Sync

A streamlined tool to extract Moodle calendar events using OpenAI's advanced AI capabilities. The system focuses on simplicity and reliability by leveraging OpenAI's Computer Use model and Agents SDK for structured data extraction.

## Simplified AI Integration

This project has been streamlined to focus exclusively on OpenAI's powerful AI technologies:

1. **OpenAI Computer Use Model**: For direct browser interaction and visual perception tasks
   - Handles complex UI navigation
   - Interprets visual elements on Moodle pages
   - Provides flexible browser automation

2. **OpenAI Agents SDK**: For structured data extraction and reasoning
   - Uses specialized agents for different tasks
   - Enables structured extraction of calendar events and course materials

### Simplified Architecture

The system now offers two implementation options:

- **Simple Implementation**: Uses only OpenAI tools for a streamlined experience
- **Hybrid Implementation**: The original implementation with additional integrations (maintained for backward compatibility)

## Project Structure

- **Core Files**:
  - `simple_moodle_scraper.py`: Streamlined scraper using only OpenAI tools
  - `hybrid_moodle_scraper.py`: Original scraper with additional integrations
  - `run.py`: Unified entry point supporting both implementations

- **Data & Logs**:
  - `data/`: Directory for storing extracted calendar events and course materials
  - `traces/`: Directory for storing agent traces for debugging

## Setup and Configuration

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. For full functionality, install the Agents SDK: `pip install openai-agents`
4. Set up your credentials:
   - Copy `.env.example` to `.env` and fill in your credentials
   - Configure OpenAI API key for Computer Use model and Agents SDK
   - Add Moodle login credentials

## Running the Application

```bash
# Extract calendar events for the next 30 days using the simple implementation (default)
python run.py calendar --days 30 --verbose

# Extract calendar events using the hybrid implementation
python run.py calendar --days 30 --scraper-type hybrid --verbose

# Extract course resources
python run.py resources --verbose

# Run with browser visible for debugging (hybrid mode only)
python run.py calendar --scraper-type hybrid --visible

# Run tests for the simple implementation
python run.py test --scraper-type simple

# Run tests for the hybrid implementation
python run.py test --scraper-type hybrid
```

### Command-line Arguments

When using the `run.py` script, the following options are available for all commands:

| Argument | Description |
|----------|-------------|
| `--skip-login` | Skip the login step (useful if already logged in) |
| `--force` | Continue even if login fails |
| `--visible` | Make the browser visible for debugging (hybrid mode only) |
| `--model MODEL` | Specify the AI model to use (default: gpt-4o) |
| `--scraper-type TYPE` | Choose between "simple" (OpenAI tools only) or "hybrid" (with additional integrations) |
| `--verbose` | Enable verbose output |

## Testing

The project includes test scripts to verify functionality:

```bash
# Test the simple implementation
python test_simple_scraper.py

# Run the test command with the simple implementation
python run.py test --scraper-type simple --verbose

# Run the test command with the hybrid implementation
python run.py test --scraper-type hybrid --verbose
```

### Test Components

The test suite verifies several key components:

1. **Agents SDK Configuration**: Validates that the Agents SDK is properly installed and configured
2. **Login Functionality**: Tests the login process with appropriate error handling
3. **Calendar Extraction**: Verifies the ability to extract events from the Moodle calendar

## Features

### Calendar Extraction
- **Authentication**: Securely logs into Moodle using stored credentials
- **Calendar Extraction**: Intelligently extracts calendar events using OpenAI tools
- **Event Structuring**: Organizes events with standardized fields (name, date, time, course, etc.)

### Course Resource Management
- **Resource Discovery**: Scans course pages for available materials and resources
- **Structured Extraction**: Organizes course materials by type, date, and relevance
- **Material Classification**: Categorizes resources (readings, assignments, lectures, etc.)

### Intelligent Automation
- **OpenAI-Powered**: Leverages the latest OpenAI models for intelligent automation
- **Model Selection**: Supports multiple AI models (gpt-4o, gpt-4.5, o1-mini, etc.)
- **Autonomous Operation**: Can run daily without user intervention

## Project History

The project has undergone significant simplification:

1. **March 2025**: Major simplification
   - Removed Puppeteer and HTML scraper integrations
   - Created streamlined implementation using only OpenAI tools
   - Maintained backward compatibility with hybrid implementation
   - Simplified overall architecture for better maintainability

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Setup

### Prerequisites

- Python 3.8 or higher
- OpenAI API key with access to Computer Use model and Agents SDK
- Moodle account at College of the Rockies

### Installation

1. Clone this repository or navigate to the project directory
2. Install dependencies: `pip install -r requirements.txt`
3. Install the Agents SDK: `pip install openai-agents`
4. Create a `.env` file with the following variables:
   ```
   OPENAI_API_KEY=your_openai_api_key
   OPENAI_AGENTS_API_KEY=your_openai_agents_api_key
   MOODLE_USERNAME=your_moodle_username
   MOODLE_PASSWORD=your_moodle_password
   ```

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OPENAI_API_KEY` | OpenAI API key for Computer Use model | Yes |
| `OPENAI_AGENTS_API_KEY` | OpenAI API key for Agents SDK (can be the same as above) | Yes |
| `MOODLE_USERNAME` | Moodle login username | Yes |
| `MOODLE_PASSWORD` | Moodle login password | Yes |
| `MOCK_LOGIN_SUCCESS` | Set to "true" to mock successful login (for testing) | No |
| `MOCK_EXTRACTION` | Set to "true" to mock successful extraction (for testing) | No |