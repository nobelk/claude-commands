---
description: Generate a detailed developer design document from product and business requirement documents
---

# Design Document Generation

You are tasked with creating a comprehensive developer design document based on the provided product and business requirement documents.

## Instructions

1. **Read and Analyze Source Documents**
   - Carefully read all provided product requirement documents (PRDs) and business requirement documents (BRDs)
   - Extract all functional and non-functional requirements
   - Identify any gaps, ambiguities, or conflicts in the requirements
   - ONLY use information explicitly stated in the provided documents - do not make assumptions or add features not mentioned

2. **Generate Design Document with the Following Sections**

   ### Executive Summary
   - Brief overview of the project and its objectives
   - Key stakeholders and target users
   - High-level scope and goals

   ### Requirements Analysis

   #### Functional Requirements
   - List all functional requirements extracted from source documents
   - Organize by feature area or user journey
   - Include acceptance criteria for each requirement

   #### Non-Functional Requirements
   - Performance requirements (response times, throughput, scalability)
   - Security requirements (authentication, authorization, data protection)
   - Availability and reliability requirements (uptime, SLAs)
   - Usability and accessibility requirements
   - Compatibility requirements (browsers, devices, platforms)
   - Compliance and regulatory requirements

   ### System Architecture
   - High-level system architecture diagram description
   - Component breakdown and responsibilities
   - Data flow between components
   - Technology stack recommendations based on requirements
   - Integration points with external systems
   - Scalability and infrastructure considerations

   ### Detailed Design
   - API specifications and endpoints
   - Database schema and data models
   - Key algorithms and business logic
   - Security implementation approach
   - Error handling and validation strategy
   - Caching and optimization strategies

   ### Quality Requirements
   - Code quality standards and guidelines
   - Code review requirements
   - Documentation requirements
   - Performance benchmarks and targets
   - Security audit requirements

   ### Testing Strategy
   - Unit testing approach and coverage targets
   - Integration testing scope
   - End-to-end testing scenarios
   - Performance and load testing requirements
   - Security testing requirements
   - User acceptance testing (UAT) plan
   - Test data requirements

   ### Monitoring and Observability
   - Logging requirements and log levels
   - Metrics and KPIs to track
   - Alerting thresholds and escalation procedures
   - APM (Application Performance Monitoring) requirements
   - Dashboard requirements
   - Incident response procedures

   ### Release Strategy
   - Deployment approach (blue-green, canary, rolling, etc.)
   - Rollback procedures
   - Database migration strategy
   - Feature flags and gradual rollout plan
   - Release phases and timeline
   - Communication plan

   ### Success Criteria
   - Measurable success metrics aligned with business goals
   - Acceptance criteria for project completion
   - Performance targets that must be met
   - User adoption and engagement targets
   - Business KPIs to track post-launch

   ### Task Breakdown
   - Break down the implementation into discrete, actionable tasks
   - Organize tasks by phase or sprint
   - Estimate complexity or effort for each task
   - Identify task dependencies and critical path
   - Assign priority levels (P0, P1, P2, P3)
   - Suggest team assignments or skill requirements

   ### Risk Assessment
   - Technical risks (technology constraints, complexity, dependencies)
   - Resource risks (team availability, skill gaps)
   - Schedule risks (dependencies, unknowns, external factors)
   - Business risks (market changes, stakeholder alignment)
   - Security risks (vulnerabilities, compliance issues)
   - For each risk, include:
     - Risk description
     - Probability (High/Medium/Low)
     - Impact (High/Medium/Low)
     - Mitigation strategy
     - Contingency plan

   ### Dependencies and Assumptions
   - External dependencies (third-party services, APIs, teams)
   - Internal dependencies (infrastructure, tools, libraries)
   - Key assumptions made in the design
   - Constraints and limitations

   ### Open Questions and Next Steps
   - Questions that need clarification from stakeholders
   - Areas requiring further investigation
   - Recommended next steps and action items

3. **Review and Verification**
   - After generating the design document, review it against the source documents
   - Verify that all requirements from the PRD/BRD are addressed
   - Check for internal consistency and coherence
   - Identify any requirements that cannot be addressed and explain why
   - Flag any assumptions or interpretations made
   - Note any missing information needed from stakeholders

4. **Output Format**
   - Generate the design document in well-formatted Markdown
   - Use clear headings, bullet points, and tables where appropriate
   - Include cross-references between sections when relevant
   - Make the document easy to navigate and review

## Important Guidelines

- **Accuracy First**: Only include information explicitly stated in or directly derivable from the source documents
- **No Feature Creep**: Do not add features, requirements, or details not mentioned in the source documents
- **Flag Gaps**: If requirements are unclear or missing information, explicitly call this out
- **Be Specific**: Provide concrete, actionable details rather than vague statements
- **Stay Grounded**: All design decisions should trace back to stated requirements
- **Review Thoroughly**: Double-check that every section addresses the actual requirements provided

## Usage

To use this command, provide the path(s) to your product and business requirement documents:

```
/design-doc path/to/prd.md path/to/brd.md
```

Or paste the content of your requirement documents after invoking the command.
