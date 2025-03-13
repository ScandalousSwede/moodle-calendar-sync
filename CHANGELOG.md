# Changelog

All notable changes to the Moodle Calendar Sync project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-03-13

### Added
- Initial release of the simplified Moodle Calendar Sync
- Created `simple_moodle_scraper.py` focusing solely on OpenAI tools
- Added support for both Computer Use model and Agents SDK
- Implemented calendar event extraction functionality
- Added course resource extraction functionality
- Created test script for the simple implementation
- Added comprehensive documentation

### Changed
- Updated `run.py` to support both simple and hybrid implementations
- Simplified requirements.txt to focus on core dependencies
- Updated README with clear instructions for the simplified approach

### Removed
- Removed dependencies on Puppeteer and HTML scrapers
- Eliminated complex integrations to improve maintainability
- Removed Google Calendar and Slack notification features from the simple implementation

## [0.2.0] - 2025-03-01

### Added
- Hybrid implementation combining OpenAI tools with traditional web scraping
- Support for Google Calendar integration
- Slack notification capabilities
- Comprehensive error handling and retry mechanisms

### Changed
- Enhanced browser automation with Playwright
- Improved credential management
- Updated documentation with detailed setup instructions

## [0.1.0] - 2025-02-15

### Added
- Initial prototype with basic Moodle scraping functionality
- Support for calendar event extraction
- Basic authentication mechanisms
- Preliminary documentation