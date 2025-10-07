# Design Document Generation

You are tasked with creating a comprehensive developer design document based on the provided product and business requirement documents.

## Instructions

### 1. Read and Analyze Source Documents

- Carefully read all provided product requirement documents (PRDs) and business requirement documents (BRDs)
- Extract all functional and non-functional requirements
- Identify any gaps, ambiguities, or conflicts in the requirements
- Create an initial inventory of all requirements with source references
- ONLY use information explicitly stated in the provided documents - do not make assumptions or add features not mentioned

### 2. Generate Design Document with the Following Sections

#### Document Metadata

```
Source Documents: [List all PRD/BRD files analyzed with versions/dates]
Analysis Date: [Date of analysis]
Requirements Count:
  - Functional: X
  - Non-Functional: Y
  - Total: Z
Coverage Summary: [To be completed in review phase]
Critical Gaps: [Number of items requiring clarification]
High-Priority Risks: [Number of items]
Estimated Effort: [T-shirt size: XS/S/M/L/XL or story points]
```

#### Executive Summary

- Brief overview of the project and its objectives
- Key stakeholders and target users
- High-level scope and goals
- Major constraints identified in source documents

#### Requirements Traceability Matrix

Create a table with the following structure:

| Req ID  | Source   | Requirement Summary  | Type           | Priority | Design Section(s)          | Status      | Notes                           |
| ------- | -------- | -------------------- | -------------- | -------- | -------------------------- | ----------- | ------------------------------- |
| REQ-001 | PRD §3.2 | User login via OAuth | Functional     | P0       | Authentication, API Design | ✓ Addressed | -                               |
| REQ-002 | BRD p.5  | 99.9% uptime SLA     | Non-Functional | P0       | Infrastructure, Monitoring | ⚠ Partial  | Needs HA strategy clarification |

Use status indicators:

- ✓ Fully Addressed
- ⚠ Partially Addressed
- ✗ Not Addressed
- ⚡ Conflicting Requirements

#### Requirements Analysis

##### Functional Requirements

For each requirement include:

- **ID**: Unique identifier (REQ-F-001, REQ-F-002, etc.)
- **Source**: Citation `[PRD Section X.Y]` or `[BRD Page N]`
- **Description**: Clear statement of the requirement
- **Acceptance Criteria**: Measurable criteria for completion
- **Priority**: P0 (Critical), P1 (High), P2 (Medium), P3 (Low)
- **Evidence Level**:
  - `[EXPLICIT]` - directly stated in source
  - `[INFERRED]` - logical inference from source material
  - `[INTERPRETATION]` - one possible reading of ambiguous source

Organize by feature area or user journey.

##### Non-Functional Requirements

Using the same structure as functional requirements, document:

- Performance requirements (response times, throughput, scalability)
- Security requirements (authentication, authorization, data protection)
- Availability and reliability requirements (uptime, SLAs)
- Usability and accessibility requirements
- Compatibility requirements (browsers, devices, platforms)
- Compliance and regulatory requirements

##### Requirements Conflicts and Resolutions

If conflicts exist between requirements:

- **Conflict ID**: Unique identifier
- **Conflicting Requirements**: REQ-X vs REQ-Y
- **Nature of Conflict**: Description
- **Proposed Resolution**: How to resolve
- **Stakeholders to Consult**: Who needs to approve resolution

#### Constraints Validation

Document all constraints explicitly stated in source documents:

- **Technical Constraints**: Technology limitations, platform restrictions
- **Budget Constraints**: Financial limits (if mentioned)
- **Timeline Constraints**: Deadlines, milestones
- **Resource Constraints**: Team size, skill availability
- **Regulatory/Legal Constraints**: Compliance requirements
- **Business Constraints**: Market windows, competitive pressures

For each constraint:

- Source citation
- Impact on design
- Verification that design stays within constraint

#### System Architecture

- High-level system architecture diagram description
- Component breakdown and responsibilities
- Data flow between components
- Technology stack recommendations **based on requirements** `[Cite: REQ-X, REQ-Y]`
- Integration points with external systems
- Scalability and infrastructure considerations
- Architecture decision records (ADRs) for major choices:
  - Decision
  - Rationale (tied to specific requirements)
  - Alternatives considered
  - Trade-offs

#### Detailed Design

- API specifications and endpoints (mapped to functional requirements)
- Database schema and data models
- Key algorithms and business logic
- Security implementation approach `[Addresses: REQ-S-001, REQ-S-005]`
- Error handling and validation strategy
- Caching and optimization strategies

**For each design element, cite the requirement(s) it addresses.**

#### Quality Requirements

- Code quality standards and guidelines
- Code review requirements
- Documentation requirements
- Performance benchmarks and targets `[Source: REQ-NF-003]`
- Security audit requirements

#### Testing Strategy

- Unit testing approach and coverage targets
- Integration testing scope
- End-to-end testing scenarios mapped to user journeys
- Performance and load testing requirements (cite NFRs)
- Security testing requirements (cite security requirements)
- User acceptance testing (UAT) plan
- Test data requirements
- Acceptance criteria verification approach

#### Monitoring and Observability

- Logging requirements and log levels
- Metrics and KPIs to track (aligned with success criteria)
- Alerting thresholds and escalation procedures
- APM (Application Performance Monitoring) requirements
- Dashboard requirements
- Incident response procedures
- How monitoring validates NFRs `[Validates: REQ-NF-001, REQ-NF-007]`

#### Release Strategy

- Deployment approach (blue-green, canary, rolling, etc.)
- Rollback procedures
- Database migration strategy
- Feature flags and gradual rollout plan
- Release phases and timeline (if specified in source documents)
- Communication plan
- Go/no-go criteria

#### Success Criteria

- Measurable success metrics aligned with business goals `[BRD §5]`
- Acceptance criteria for project completion
- Performance targets that must be met (cite NFRs)
- User adoption and engagement targets (if specified)
- Business KPIs to track post-launch
- Definition of Done

#### Task Breakdown

Break down the implementation into discrete, actionable tasks:

| Task ID  | Description                 | Requirements Addressed | Phase/Sprint | Effort | Dependencies | Priority | Skills Required   | Status  |
| -------- | --------------------------- | ---------------------- | ------------ | ------ | ------------ | -------- | ----------------- | ------- |
| TASK-001 | Implement OAuth integration | REQ-F-001              | Sprint 1     | 5 SP   | None         | P0       | Backend, Security | Pending |
| TASK-002 | Design HA architecture      | REQ-NF-002             | Sprint 1     | 8 SP   | TASK-001     | P0       | DevOps, Architect | Pending |

- Organize tasks by phase or sprint
- Estimate complexity or effort for each task
- Identify task dependencies and critical path
- Assign priority levels (P0, P1, P2, P3)
- Suggest team assignments or skill requirements

#### Risk Assessment

For each risk, provide:

| Risk ID  | Category  | Description                 | Probability | Impact | Requirements at Risk  | Mitigation Strategy                   | Contingency Plan               | Owner     |
| -------- | --------- | --------------------------- | ----------- | ------ | --------------------- | ------------------------------------- | ------------------------------ | --------- |
| RISK-001 | Technical | Third-party API rate limits | Medium      | High   | REQ-F-003, REQ-NF-005 | Implement caching and request queuing | Switch to alternative provider | Tech Lead |

Categories:

- Technical risks (technology constraints, complexity, dependencies)
- Resource risks (team availability, skill gaps)
- Schedule risks (dependencies, unknowns, external factors)
- Business risks (market changes, stakeholder alignment)
- Security risks (vulnerabilities, compliance issues)
- Integration risks (external dependencies, APIs)

#### Dependencies and Assumptions

##### External Dependencies

For each dependency:

- **Dependency**: What we depend on
- **Owner**: Who provides it
- **SLA/Timeline**: When we need it
- **Risk**: What if it's not available
- **Requirements Affected**: Which requirements need this

##### Internal Dependencies

- Infrastructure requirements
- Tools and libraries needed
- Team dependencies
- Environment setup needs

##### Assumptions

For each assumption:

- **Assumption**: The assumption itself
- **Rationale**: Why this assumption is necessary (what information is missing)
- **Source Gap**: `[Gap: PRD does not specify X]`
- **Risk if Wrong**: Impact if assumption is invalidated
- **Validation Needed From**: Stakeholder who needs to confirm
- **Impact on Design**: What would change if invalidated
- **Requirements Affected**: Which requirements depend on this

##### Constraints and Limitations

Document technical, business, and regulatory constraints.

#### Open Questions and Next Steps

##### Critical Questions Requiring Clarification

For each question:

- **Question**: The specific question
- **Context**: Why this is important
- **Blocking**: Which requirements or tasks are blocked
- **Stakeholder**: Who can answer
- **Impact**: What happens if not answered

##### Areas Requiring Further Investigation

- Technical spikes needed
- Proof of concepts required
- Research or prototyping work

##### Recommended Next Steps

1. Prioritized action items
2. Stakeholder reviews needed
3. Technical validations required

### 3. Review and Verification

After generating the design document, perform these verification steps:

#### Requirements Coverage Checklist

- [ ] All functional requirements from PRD are addressed
- [ ] All non-functional requirements from BRD are addressed
- [ ] All requirements have source citations
- [ ] No features added beyond source documents
- [ ] All design decisions trace back to stated requirements
- [ ] Traceability matrix is complete and accurate

#### Quality Assurance

- [ ] Internal consistency verified (no contradictions)
- [ ] All assumptions documented and justified
- [ ] All gaps and ambiguities flagged with specific questions
- [ ] All risks have mitigation strategies
- [ ] All constraints validated
- [ ] Cross-references between sections are accurate

#### Coverage Analysis

Calculate and report:

- **Fully Addressed**: X requirements (Y%)
- **Partially Addressed**: N requirements (M%) - with explanation for each
- **Not Addressed**: P requirements (Q%) - with rationale for each
- **Conflicting**: R requirement conflicts identified and resolved

#### Evidence Trail

For key design decisions, verify:

- Decision can be traced to specific requirement(s)
- Citation format is consistent: `[PRD §X.Y]`, `[BRD p.N]`
- Inferences are marked as `[INFERRED]`
- Interpretations are marked as `[INTERPRETATION]`
- Gaps are marked as `[GAP]` with specific missing information

#### Final Validation Report

Summarize:

```
DESIGN DOCUMENT VALIDATION REPORT
==================================
Total Requirements: X
- Functional: Y
- Non-Functional: Z

Coverage:
- Fully Addressed: A (B%)
- Partially Addressed: C (D%)
- Not Addressed: E (F%)

Critical Issues:
- Conflicting Requirements: N
- Assumptions Requiring Validation: M
- Blocking Questions: P
- High-Priority Risks: Q

Confidence Level: [High/Medium/Low]
Ready for Review: [Yes/No]
Next Steps: [List 3-5 immediate actions needed]
```

### 4. Output Format

- Generate the design document in well-formatted Markdown
- Use clear headings, bullet points, and tables where appropriate
- Include cross-references between sections when relevant
- Use consistent citation format throughout
- Make the document easy to navigate and review
- Include table of contents with section links
- Use color-coding or symbols for requirement status:
  - ✓ Fully Addressed
  - ⚠ Partially Addressed
  - ✗ Not Addressed
  - ⚡ Conflicting
  - ❓ Needs Clarification

## Important Guidelines

- **Accuracy First**: Only include information explicitly stated in or directly derivable from the source documents
- **No Feature Creep**: Do not add features, requirements, or details not mentioned in the source documents
- **Flag Gaps**: If requirements are unclear or missing information, explicitly call this out with specific questions
- **Be Specific**: Provide concrete, actionable details rather than vague statements
- **Stay Grounded**: All design decisions should trace back to stated requirements with citations
- **Review Thoroughly**: Double-check that every section addresses the actual requirements provided
- **Cite Everything**: Every requirement, constraint, and decision should have a source citation
- **Mark Uncertainty**: Use `[EXPLICIT]`, `[INFERRED]`, `[INTERPRETATION]`, `[ASSUMPTION]`, `[GAP]` tags
- **Quantify Coverage**: Provide specific numbers and percentages for requirement coverage
- **Bidirectional Traceability**: Ensure requirements trace to design AND design traces back to requirements

## Pre-Submission Validation Checklist

Before presenting the design document, verify:

- [ ] All functional requirements from PRD are covered in traceability matrix
- [ ] All non-functional requirements from BRD are covered in traceability matrix
- [ ] Every requirement has a source citation
- [ ] Every design decision cites the requirement(s) it addresses
- [ ] No features or capabilities added beyond source documents
- [ ] All assumptions documented with risk assessment
- [ ] All gaps/ambiguities flagged with specific questions
- [ ] All conflicts identified and resolution proposed
- [ ] Traceability matrix complete with status for each requirement
- [ ] Internal consistency verified (no contradictions)
- [ ] Technical feasibility assessed for all components
- [ ] Coverage percentage calculated and reported
- [ ] Validation report completed
- [ ] Document metadata filled out completely
- [ ] Cross-references are accurate
- [ ] Citation format is consistent

## Common Pitfalls to Avoid

1. **Adding unstated features**: Only design what is explicitly required
2. **Missing citations**: Every requirement and design decision needs a source
3. **Vague requirements**: If source is vague, flag it - don't guess
4. **Unmarked assumptions**: All assumptions must be explicitly documented
5. **Incomplete traceability**: Every requirement must map to design elements
6. **Ignoring conflicts**: Document and propose resolution for all conflicts
7. **Over-engineering**: Don't add complexity not justified by requirements
8. **Under-specifying NFRs**: If performance/security/reliability targets unclear, flag them
9. **Missing validation**: Always complete the verification checklist
10. **Poor citation**: Use specific section/page numbers, not just "PRD" or "BRD"
