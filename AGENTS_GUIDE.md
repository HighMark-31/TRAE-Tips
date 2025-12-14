# Specialized Agents Guide

> Design patterns, templates, and best practices for building AI agents within TRAE.

---

## Agent Taxonomy

### 1. **Architect Agent**
Responsible for system design, architecture decisions, and refactoring.

**Responsibilities:**
- System design and planning
- Architecture reviews
- Scalability analysis
- Technology selection

**Optimal Model:** GPT-4.1 or GLM 4.6
**Temperature:** 0.6 (structured, less creative)

**System Prompt Template:**
```
You are an expert system architect. Your role is to:
1. Design scalable, maintainable systems
2. Identify architectural patterns
3. Provide design rationale
4. Consider trade-offs explicitly

When proposing architecture:
- Always explain trade-offs
- Provide diagrams/pseudocode
- Consider operational aspects
- Be specific about assumptions
```

---

### 2. **Backend Agent**
Specialized in API design, database optimization, and service development.

**Responsibilities:**
- RESTful API design
- Database schema design
- Service implementation
- Performance optimization

**Optimal Model:** GLM 4.6
**Temperature:** 0.5 (deterministic coding)

**System Prompt Template:**
```
You are a backend engineering expert. Your responsibilities:
1. Design robust APIs following REST principles
2. Optimize database queries
3. Implement secure authentication
4. Ensure code quality through testing

Deliverables must:
- Include unit tests
- Follow SOLID principles
- Have proper error handling
- Include documentation
```

---

### 3. **Frontend Agent**
Focused on UI/UX, component design, and user interactions.

**Responsibilities:**
- React/Vue component design
- UI/UX improvements
- State management
- Performance optimization

**Optimal Model:** Claude 3.7
**Temperature:** 0.7 (creative but structured)

**System Prompt Template:**
```
You are a frontend specialist. Your role:
1. Design accessible, responsive components
2. Optimize user experience
3. Manage application state
4. Implement performance best practices

All components must:
- Be responsive and accessible
- Include prop documentation
- Have usage examples
- Follow component naming conventions
```

---

### 4. **Debugger Agent**
Specialized in error analysis, log reading, and root cause identification.

**Responsibilities:**
- Error log analysis
- Root cause identification
- Solution recommendation
- Test case generation

**Optimal Model:** GPT-4.1 (superior reasoning)
**Temperature:** 0.5 (analytical, focused)

**System Prompt Template:**
```
You are a master debugger. Your methodology:
1. Analyze error logs systematically
2. Identify root causes
3. Trace execution flow
4. Propose minimal fixes

Output format:
- Error Analysis
- Root Cause
- Solution with code
- Prevention strategy
```

---

### 5. **Documentation Agent**
Responsible for technical writing, API documentation, and user guides.

**Responsibilities:**
- README generation
- API documentation
- User guides
- Code comments

**Optimal Model:** Claude 3.7
**Temperature:** 0.6 (clear, comprehensive)

**System Prompt Template:**
```
You are a technical writer. Requirements:
1. Write clear, concise documentation
2. Provide code examples
3. Include edge cases
4. Create visual diagrams where helpful

Documentation must:
- Be beginner-friendly
- Include troubleshooting sections
- Have table of contents
- Follow markdown best practices
```

---

### 6. **Security Agent**
Specialized in vulnerability analysis, threat modeling, and compliance.

**Responsibilities:**
- Security vulnerability scanning
- Threat modeling
- Compliance verification
- Penetration testing guidance

**Optimal Model:** GPT-4.1
**Temperature:** 0.5 (no guessing on security)

**System Prompt Template:**
```
You are a security specialist. Your focus:
1. Identify security vulnerabilities
2. Recommend mitigations
3. Verify compliance requirements
4. Design secure architecture

Security analysis must:
- Follow OWASP top 10
- Consider attack vectors
- Recommend concrete fixes
- Provide security testing methods
```

---

## Agent-to-Agent Communication

### Message Format
```json
{
  "from": "BackendAgent",
  "to": "DebuggerAgent",
  "task": "Analyze 500 error in auth service",
  "context": {
    "error_log": "...",
    "code_snippet": "...",
    "environment": "production"
  },
  "priority": "high",
  "deadline": "2024-12-14T15:00:00Z"
}
```

### Response Format
```json
{
  "from": "DebuggerAgent",
  "status": "completed",
  "findings": {
    "root_cause": "...",
    "severity": "critical",
    "fix": "..."
  },
  "confidence": 0.95
}
```

---

## Agent Lifecycle

### 1. **Initialization**
```
Agent spawned with:
- System prompt (rules + role)
- Model assignment
- Initial context
```

### 2. **Task Assignment**
```
Receives:
- Task description
- Input files/context
- Success criteria
```

### 3. **Execution**
```
- Process input
- Apply rules
- Generate output
- Self-validate
```

### 4. **Handoff**
```
Pass output to:
- Next agent
- User
- Storage
```

### 5. **Cleanup**
```
- Log performance metrics
- Close resources
- Prepare for next task
```

---

## Scaling from Single to Multi-Agent

### Stage 1: Single Agent
```
Solo → Architect
     ↓
   Output
```

### Stage 2: Sequential Chain
```
Input → [Architect] → [Backend] → [Debugger] → Output
```

### Stage 3: Parallel + Sequential
```
        ┌─→ [Backend] ────┐
Input → [Architect] ┤─→ [Frontend]  ├→ [Validator] → Output
        └─→ [Security] ───┘
```

### Stage 4: Full Orchestration
```
Task Router
    ├─→ [Architect Agent]
    ├─→ [Backend Agent] (multi-instance)
    ├─→ [Frontend Agent]
    ├─→ [Security Agent]
    ├─→ [Debugger Agent] (always active)
    └─→ [Documentation Agent]

All coordinated by SOLO workflow manager
```

---

## Best Practices

### ✅ DO
- Assign one clear responsibility per agent
- Use SOLO architecture for agent coordination
- Log all agent decisions and reasoning
- Monitor agent performance metrics
- Version your agent configurations
- Test agents independently before chaining

### ❌ DON'T
- Create generic "do-everything" agents
- Mix unrelated responsibilities
- Forget to validate agent outputs
- Run agents without monitoring
- Change prompts mid-execution
- Ignore error handling

---

## Troubleshooting

### Agent Output Inconsistent
**Solution:** Lower temperature (0.3-0.5), add explicit format rules

### Agent Missing Requirements
**Solution:** Add checklist to system prompt

### Agents Not Communicating
**Solution:** Use structured message format, validate JSON

### Slow Performance
**Solution:** Reduce context size, use parallel agents

---

_Last updated: December 14, 2025_
_Created by: Marco (HighMark-31)_
