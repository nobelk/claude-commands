# Claude Commands for Software Engineering

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

A collection of tested Claude commands designed to streamline common software engineering tasks. These commands provide structured workflows for code analysis, debugging, root-cause analysis, and quality assurance.


## Available Commands

### 🔍 Code Review Command

**File**: [`code_review.md`](code_review.md)

**Purpose**: Perform comprehensive pull request analysis with structured feedback

**Usage**:
```
Review the code and unit tests in the pull request: <PR_NUMBER|PR_URL|BRANCH_NAME>
```

**Features**:
- **Automated PR Context Gathering**: Fetches PR information, diffs, commit history, and changed files
- **Multi-dimensional Analysis**:
  - Code Quality & Design (SOLID principles, design patterns, DRY)
  - Implementation Review (bugs, edge cases, error handling)
  - Security Analysis (vulnerabilities, authentication, data exposure)
  - Performance Considerations (bottlenecks, scalability)
  - Test Coverage Analysis (coverage calculation, test quality)
  - Documentation & Maintainability
- **Prioritized Findings**: Categorizes issues as CRITICAL, HIGH, MEDIUM, or LOW priority
- **Structured Output**: Executive summary, detailed findings, positive aspects, and actionable items
- **Code Examples**: Provides before/after code snippets for improvements

### 🐛 Root Cause Analysis (RCA) Command

**File**: [`rca.md`](rca.md)

**Purpose**: Analyze exceptions and provide comprehensive fixes with unit tests

**Usage**:
```
Analyze the exception details in <EXCEPTION_FILE> and identify the root cause...
```

**Features**:
- **Exception Parsing**: Extracts exception type, message, stack trace, and context
- **Systematic Investigation**:
  - Primary failure point analysis
  - Call chain tracing
  - Context gathering from related files
- **Root Cause Identification**: Covers common patterns including:
  - Spring Boot specific issues (bean initialization, circular dependencies)
  - Database and JPA/Hibernate problems
  - Multi-tenancy and AWS integration issues
  - OpenSearch and JOOQ-related problems
- **Comprehensive Solutions**:
  - Exact code fixes with file paths and line numbers
  - Defensive programming and error handling
  - Performance and thread safety considerations
- **Test Generation**: Creates unit tests to reproduce issues and validate fixes
- **Verification Steps**: Provides clear instructions for testing and rollback

## Command Structure

Each command follows a structured approach:

1. **Input Validation**: Ensures required parameters are provided
2. **Context Gathering**: Collects relevant information from the codebase
3. **Systematic Analysis**: Applies domain-specific expertise
4. **Structured Output**: Provides actionable, prioritized recommendations
5. **Verification**: Includes steps to validate the results

## Benefits

- **Consistency**: Standardized analysis approaches across different scenarios
- **Thoroughness**: Comprehensive coverage of multiple quality dimensions
- **Actionability**: Prioritized, specific recommendations with examples
- **Documentation**: Clear output formats for team collaboration
- **Best Practices**: Incorporates industry standards and framework-specific knowledge

## Getting Started

1. Choose the appropriate command for your task
2. Follow the usage pattern specified in each command file
3. Provide the required inputs (PR identifier, exception file, etc.)
4. Review the structured output and implement recommendations

## Contributing

When adding new commands:
- Follow the established structure and formatting
- Include comprehensive analysis steps
- Provide clear usage examples
- Test commands with real scenarios
- Update this README with new command documentation

## License

Licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.
